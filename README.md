# Data flow Diagram SDK

This document describes the software development kit (SDK) enabling iOS applications to use dataflow diagrams that implement specific algorithms to process timestamped sensor data as for example generated a motion capture system (see our [Motion Capture SDK](https://github.com/Proavatar/MotionCaptureSDK.git)) and calculate specific output values.

For a detailed description, refer to the document “[Dataflow programming method](https://docs.google.com/document/d/1dgqtAdi8aAYIHrEZM6oJKXcoKWhqdTFBfdjuou_s0sQ/preview)”.

The SDK is offered as a Swift Package containing the binary framework that implements the following functionality:
* Create a new dataflow diagram and fill it with a specified algorithm.
* Retrieve information from the dataflow diagram.
* Changing the diagram constants.
* Update the inputs of a diagram.
* Reset the temporal state of the dataflow diagram.

The package will be downloaded and added to your project.

By default the SDK can be used without a license, but only allows loading diagrams with a maximum of two input streams. To remove this limitation, a license is required.

>To request a license, please contact [sales@proavatar.io](mailto:sales@proavatar.io?subject=Dataflow%20Diagram%20SDK%20license%20request).

All required functionality is implemented in the `DataflowDiagram` class. To use this class, place the following import in your Swift files:

```Swift
import DataflowDiagramSDK
```

For a complete SDK reference, download the document "[Dataflow algorithms SDK specification](https://docs.google.com/document/d/15MEn8yUazdlI-V9CQ2xBGTLxf31o_bOUaY-FbKQJfmY/preview)".
