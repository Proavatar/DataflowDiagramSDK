## Dataflow Diagram SDK

This following describes the software development kit (SDK) enabling iOS applications to use dataflow diagrams that implement specific algorithms to process timestamped sensor data as for example generated a motion capture system (see our [Motion Capture SDK](https://github.com/Proavatar/MotionCaptureSDK.git)) and calculate specific output values.

>A detailed explanation of the dataflow programming method, can be found [here](https://proavatar.github.io/DataflowDiagramSDK/).

The SDK is offered as a Swift Package that implements the following functionality:
* [Create a new dataflow diagram and fill it with a specified algorithm](#creating-a-dataflow-diagram).
* [Retrieve information from the dataflow diagram](#dataflow-diagram-information).
* [Changing the diagram constants](#changing-diagram-constants).
* [Update the inputs of a diagram](#diagram-update).
* [Reset the temporal state of the dataflow diagram](#resetting-the-diagram).

In the following this functionality is described in more detail.

## Installing the SDK

The SDK is available as a Swift package and can be installed as part of your Xcode Swift project.

The SDK is named “DataflowDiagramSDK” and is available as a Swift package via GitHub under the URL:
https://github.com/Proavatar/DataflowDiagramSDK.git

To install the “DataflowDiagram” Swift package in your project, perform the following steps in Xcode:
1. In the Project Editor select your project.
2. Select the tab “Package Dependencies”.
3. Click the + button.
4. In the search bar add the URL to the GitHub repository.
5. Press the “Add Package” button.

The package will be downloaded and added to your project.
All required functionality is implemented in the `DataflowDiagram` class. To use this class, place the following import in your file:

```swift
import DataflowDiagramSDK
```

By default the SDK can be used without a license, but only allows loading diagrams with a maximum of two input streams. To remove this limitation, a license is required.

>To request a license, please contact [sales@proavatar.io](mailto:sales@proavatar.io?subject=Dataflow%20Diagram%20SDK%20license%20request).

## Dataflow diagram I/O

Consider an algorithm that takes one or more sensor data streams as *input* and calculates some kind of *output*. Such an algorithm is constructed - or implemented - by creating a *dataflow diagram* that uses *input streams* and a number of interconnected *functions* to calculate the value of one or more *variable outputs* of specific types. These can then be used by a connected reporting system like a graphical user interface (GUI) for example. Any settings of the diagram – that can be changed by the executing application – are implemented by using *constants*.

The architecture of an algorithm is given in the figure below.

![Algorithm architecture](https://docs.google.com/drawings/d/e/2PACX-1vSvBzU94EUyZuSgtF89ilkc0b4H9OGCylEuF5Fz3cElTkvVr_sJM2TJnrOXAU-hm-K4ul-KwO1VXV1r/pub?w=861&h=319)

For the dataflow diagram I/O two structures are defined:

```swift
struct DataflowDiagramInput
{
    let timestamp : TimeInterval
    var updates   : [String:Any]
}

struct DataflowDiagramOutput
{
    let timestamp : TimeInterval
    var outputs   : [String:Any]
}
```

## Variable types

In a dataflow diagram several timestamped variables can be used. For example, the orientation of a segment is a timestamped orientation and the position of a joint is a timestamped vector.
In the following table the variable types are defined that can be used in a dataflow diagram.

| Name          | Type         | Description                      |
| :--------------|:--------------|:----------------------------------|
| Float         | `Double`      | Floating point value, used for angles and other values. |
| Integer       | `Int`        | Integer value, used for indices and numbers. |
| Vector        | `simd_double3` | A 3D position (x,y,z).            |
| Boolean       | `Bool`       | Logical value, i.e. true or false. |
| Orientation   | `simd_quatd` | An orientation, expressed as a quaternion (x,y,z,w). |
| Array         | `[Double]`   | A collection of floats, i.e. [f<sub>0</sub> , ... , f<sub>N-1</sub>]. |
| Sequence      | `[(t:Double,f:Double)]` | An array of timestamped floats, i.e. [(t<sub>0</sub> , f<sub>0</sub>) , ... , (t<sub>N-1</sub> , f<sub>N-1)</sub>]. |
| String        | `String`     | A piece of text. |

Import `simd` for using the `simd_double3` and `simd_quatd` types.

## Creating a dataflow diagram

Before a dataflow diagram can be used to run a specific algorithm, an instance of the `DataflowDiagram` class must be created.

### Update protocol
The dataflow diagram will indicate the updates of the variable outputs using the `VariableOutputUpdatesReceiver` protocol which has two functions.

```swift
protocol VariableOutputUpdatesReceiver : AnyObject
{
    func newVariableOutputUpdates(_ output: DataflowDiagramOutput )
    func allUpdatesProcessed(_ outputs: [DataflowDiagramOutput] )
}
```

As such, any object in the application that is going to process these updates needs to comply with this protocol and implement these functions.

### Instantiation
To instantiate a dataflow diagram the initialization method takes the reference to the object in the application that complies with the `VariableOutputUpdatesReceiver` protocol.
```swift
DataflowDiagram( variableOutputUpdatesReceiver: VariableOutputUpdatesReceiver? = nil )
```
This creates an empty dataflow diagram which needs to be filled by supplying the JSON representation of the diagram as described in the next section.

### License activation
By default, without a license the SDK can be used with a maximum of two input streams. To remove this limitation, a commercial license is required.
To activate the license, the `activateLicense()` method must be called.

```swift
func activateLicense( licenseKey: String, bundleId: String )
```

To obtain a license, please contact sales@proavatar.io.

### Fill the diagram
The contents of a dataflow diagram is specified by a JSON string which can be stored in a standard text file or retrieved via an API to an online cloud platform. As such, once the application retrieves the JSON string, it can be used to fill the dataflow diagram by calling the `read()` method.
```swift
func read( from jsonString: String, replace: Bool = true ) -> Bool
```
When a valid JSON string is supplied, the function returns `true` otherwise the JSON string contains an error.
The function also has an optional parameter replace which by default is `true` which means that any diagram currently present will be overridden. However, when this value is set to `false`, the JSON string is used to extend the diagram. This could be used to combine two diagrams.

## Dataflow diagram information
When a diagram is filled (see “[Fill the diagram](#fill-the-diagram)”), it can be important for the application to know which input streams are used and what variable outputs the diagram can calculate. The diagram can also contain some manual lines which might contain usage information or the type of exercises that can be processed by the diagram for example.

### Used input streams
Which input streams the diagram uses is important information for the application to know which information must be supplied. To retrieve the used input streams the `getInputStreams()` method of the dataflow diagram must be called.
```swift
func getInputStreams() -> [(label:String, typeString:String)]
```
The output of the function is an array of tuples containing the label of the input stream and its type as described in “[Variable types](#varaible-types)” (e.g. “Float”, “Integer”, “Vector”, et cetera).

### Specified variable outputs
To prepare the application for the outputs the diagram can calculate, it can be helpful to have the ability to retrieve the list of specified outputs. To retrieve this list, the `getVariableOutputs()` method of the dataflow diagram must be called.
```swift
func getVariableOutputs() -> [(label:String, typeString:String)]
```
The output of the function is an array of tuples containing the label of the output variable and its type as described in “[Variable types](#varaible-types)” (e.g. “Float”, “Integer”, “Vector”, et cetera).

### Get manual lines
The dataflow diagram could have some manual lines which might contain usage information which might be useful information for the application. To obtain these lines the ``getManualLine()`` method of the dataflow diagram must be called.
```swift
func getManualLines() -> [String]
```

### Create JSON representation
As described in “[Fill the diagram](#fill-the-diagram)”, a dataflow diagram is specified by means of a JSON string. In order for the application to save a diagram or forward it, the JSON string can be created by calling the `createJSON()` method of the dataflow diagram.
```swift
func createJSON() -> String
```

## Changing diagram constants

In most cases constants are used in a diagram to indicate a setting for a specific function, like defining the vertical axis or an integer for a buffer size. However, there are also constants that can be considered as parameters for the algorithm, indicating for example the required time to complete a cycle or thresholds for joint angles, etc. This chapter describes the functionality by which the application can change these constants.

### Specified constants
To be able to know which constants are used in the diagram, the `getConstants()` method of the dataflow diagram can be called.
```swift
func getConstants() -> [(label:String, value:Any)]
```
In a diagram it is not mandatory to specify a label for each constant. As such, there might be constants which have no label. The function however will only return those constants for which a label is defined. The labels of the constants don’t have to be unique. As such a label could be present multiple times in the returned array.

### Change constant value
To be able to change the value of a constant, the `setConstant()` method of the dataflow diagram can be called.
```swift
func setConstant( label:String, newValue:Any )
```
As mentioned above, there can be constants with the same label. Calling the function will change the value for all constants with the specified label. The constant will only be set when the type of the supplied `newValue` parameter matches that of the constant (i.e. as returned by the `getConstants()` method described in "[Specified constants](#specified-constants)").

## Diagram update

As described in “[Dataflow diagram I/O](#dataflow-diagram-io)”, the application must supply the updates for the diagram which it can use to calculate the outputs.

### Update the input streams
Whenever the application has updated information, it needs to create a `DataflowDiagramInput` struct variable and set the `timestamp` field, fill the `updates` dictionary field with the names of the input streams in the diagram. The created variable is then used in a call of the `updateInputStreams()` method of the dataflow diagram.

```swift
func updateInputStreams( diagramInput : DataflowDiagramInput  )
```

When the `updates` dictionary contains names that are not part of the diagram's input streams, these are simply ignored.

### Receive updated variable outputs
When the update results in one or more updates for the specified variable outputs, the delegate's `newVariableOutputUpdates()` protocol function will be called as described in “[Update protocol](#update-protocol)” and repeated below for reference.

```swift
func newVariableOutputUpdates(_ output: DataflowDiagramOutput )
```
### Process an array of updates
When processing for example a file, the processing can be performed in on batch. To do this, the application needs to create an array of `DataflowDiagramInput` structs and for each element in this array set the `timestamp` field and fill the `updates` dictionary field with the names of the input streams in the diagram. The created array is then used in a call of the `processAllUpdates()` method of the dataflow diagram.

```swift
func processAllUpdates( diagramInputs: [DataflowDiagramInput] )
```

The processing will be performed in the background and when finished, the delegate's `allUpdatesProcessed()` protocol function will be called as described in “[Update protocol](#update-protocol)” and repeated below for reference.

```swift
func allUpdatesProcessed(_ outputs: [DataflowDiagramOutput] )
```

### Read input from a JSONL file

The SDK offers a functionality to process data when it is available as JSON lines (i.e. using newline '\n' character as line separation). An example is given below.

```json
{"timestamp":12.34,"name":"Left upper leg","orientationValue":{"x":0.2345,"y":0.1234,"z":0.123,"w":0.92}}
{"timestamp":12.34,"name":"Left lower leg","orientationValue":{"x":0.1234,"y":0.0221,"z":0.002,"w":0.82}}
{"timestamp":12.54,"name":"Left upper leg","orientationValue":{"x":0.1345,"y":0.4234,"z":0.163,"w":0.92}}
{"timestamp":12.54,"name":"Left lower leg","orientationValue":{"x":0.1334,"y":0.0221,"z":0.002,"w":0.42}}
```

The JSON schema for a line in a data file is given below.
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "timestamp": {"type": "number"},
    "name": {"type": "string"},
    "floatValue": {"type": "number"},
    "integerValue": {"type": "integer"},
    "vectorValue": {
      "type": "object",
      "properties": {
        "x": {"type": "number"},
        "y": {"type": "number"},
        "z": {"type": "number"}
      },
      "required": ["x", "y", "z"]
    },
    "booleanValue": {"type": "boolean"},
    "orientationValue": {
      "type": "object",
      "properties": {
        "x": {"type": "number"},
        "y": {"type": "number"},
        "z": {"type": "number"},
        "w": {"type": "number"}
      },
      "required": ["x", "y", "z", "w"]
    },
    "stringValue": {"type": "string"}
  },
  "required": ["timestamp", "name"]
}
```

To process a JSONL string (as read from a file), the `readDataflowDiagramInputs()` function can be called.

```swift
func readDataflowDiagramInputs( from jsonLines: String ) -> [DataflowDiagramInput]
```

The returned array can then be used in a call to the `processAllUpdates()` method as described in "[Process an array of updates](#process-an-array-of-updates)".

### Write to JSONL file

When an array of diagram inputs is available (for example after a recording), these can be converted into a JSONL file which can be read in later as described in "[Read input from a JSONL file](#read-input-from-a-jsonl-file)". This is done by calling the `createJsonLines()` function.

```swift
func createJsonLines( from dataflowDiagramInputs : [DataflowDiagramInput] ) -> String
```

### Hide variable outputs
By default, all updated variable outputs are offered to the application via the `newVariableOutputUpdates()` protocol function (see "[Receive updated variable outputs](#receive-updated-variable-outputs)"). However, as it is possible to have variable outputs that have linked input streams (to allow for diagram loops), it can be preferred that some variable outputs are hidden in order for their updates not to be forwarded to the application, but can still be used by linked input streams. To control the visibility of a variable output, the `setVariableOutputHidden()` method can be called.
```swift
func setVariableOutputHidden( label:String, hidden:Bool )
```

### Disable forwarding of input streams
By default, all updates of input streams are also forwarded as output of the diagram and are offered to the application via the  `newVariableOutputUpdates()` protocol function (see "[Receive updated variable outputs](#receive-update-variable-outputs)"). This can for example be used when using animation of segments. This can be disabled by calling the `setInputStreamForwarding()` method.
```swift
func setInputStreamForwarding( label:String, forwarding:Bool )
```
Note that the application could use the type (see “[Variable types](#variable-types)”) to determine how to use or present it.

## Resetting the diagram
While the inputs are updated, the internal temporal state of the diagram changes as it can contain buffers or the update for some functions might be pending because not all the inputs are updated yet.

To be able to remove any history from the diagram and set the diagram to a state as if no update occurred yet, the `reset()` method of the dataflow diagram can be called.
```swift
func reset()
```

## String representations

### Get the string from value
To get the string representation of a dataflow diagram output value, the `getValueString()` function can be called.

```swift
func getValueString(_ value : Any ) -> String
```

### Set the value from a string

To set the value from a string, the `func setValueFromString()` function can be called.

```swift
func setValueFromString( value: inout Any, string: String )
```
