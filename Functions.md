# Function list

<table>
  <tr>
   <td>Name
   </td>
   <td>Inputs
   </td>
   <td>Output
   </td>
  </tr>
  <tr>
   <td>Absolute
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The absolute value of the float.
   </td>
  </tr>
  <tr>
   <td>Add
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The addition operation is performed on the two generic inputs which are of the same type. Unsupported types: Boolean and Boolean array. 
   </td>
  </tr>
  <tr>
   <td>Add to array
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
A copy of the array with the float value is added to the end.
   </td>
  </tr>
  <tr>
   <td>Adder
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
Sum of all previous updates.
   </td>
  </tr>
  <tr>
   <td>And
   </td>
   <td>
<ol>

<li>Boolean

<li>Boolean
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
The logical AND operation between the two booleans.
   </td>
  </tr>
  <tr>
   <td>Array absolute
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
A copy of the array with all its elements converted to their absolute values.
   </td>
  </tr>
  <tr>
   <td>Array sum
   </td>
   <td>
<ol>

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic value</span>
<p>
The sum of all the elements in the array. Unsupported types are: Boolean array and Sequence array.
   </td>
  </tr>
  <tr>
   <td>Average
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The average value of the elements in the array.
   </td>
  </tr>
  <tr>
   <td>Averager
   </td>
   <td>
<ol>

<li>Boolean

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
Sum of all previous updates of the float input during the time the boolean input is <em>true</em>, divided by the number of updates.
   </td>
  </tr>
  <tr>
   <td>Buffer
   </td>
   <td>
<ol>

<li>Integer

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The generic input delayed by the number of updates specified by the integer input. When the generic input is updated, the new value is stored in an internal array. When the size of this array is larger than the current value of the integer input, the oldest elements are removed to correct the size. After this is done, the first element in the array is forwarded to the output.  
   </td>
  </tr>
  <tr>
   <td>Cap values
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A copy of the sequence input for which the value of all samples are limited to fall between the first and second float.
   </td>
  </tr>
  <tr>
   <td>Centered moving average
   </td>
   <td>
<ol>

<li>Integer

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence containing the centered moving average of the input sequence where the size of the averaging window is specified by the integer input. The output is generated when the sequence input is updated.
   </td>
  </tr>
  <tr>
   <td>Clip
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
A copy of the input array but with all elements removed that are smaller than the first float input or larger than the second float input.
   </td>
  </tr>
  <tr>
   <td>Combine arrays
   </td>
   <td>
<ol>

<li>Integer

<li>Generic array

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
A new array in which the first array input is added into the second array input at the 0-based index specified by the integer input.
   </td>
  </tr>
  <tr>
   <td>Convert to sequence
   </td>
   <td>
<ol>

<li>Float array

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence with the timestamps specified by the first array input and the values by the second.
   </td>
  </tr>
  <tr>
   <td>Cosine
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The cosine value of the input float.
   </td>
  </tr>
  <tr>
   <td>Create array
   </td>
   <td>
<ol>

<li>Integer

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
The updates of the value input are stored internally in an array. The array is offered as the output when the number of elements in the array is equal to the value of the integer input. Each time the value input updates the new value is added to the array and the oldest element is removed.
   </td>
  </tr>
  <tr>
   <td>Create sequence
   </td>
   <td>
<ol>

<li>Boolean

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
When the boolean is updated to <em>true</em> an empty sequence is created internally and all subsequent updates of the float value are added as samples. When the boolean input becomes <em>false</em>, the output is updated with the created sequence.
   </td>
  </tr>
  <tr>
   <td>Degrees to radians
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The input float is multiplied by π and then divided by 180.
   </td>
  </tr>
  <tr>
   <td>Delay
   </td>
   <td>
<ol>

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The value of the second float and its timestamp are buffered internally. Whenever a new update is received for that float, the buffered samples are used to calculate the interpolated value the float would have had at the time in the past specified by the current time minus the value of the second float.
   </td>
  </tr>
  <tr>
   <td>Derivative
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The time derivative of the float, calculated by taking the difference between the current and previous values, and dividing it by the difference between the current and previous timestamps, yielding the rate of change of the input float.
   </td>
  </tr>
  <tr>
   <td>Distance
   </td>
   <td>
<ol>

<li>Vector

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The distance between the two points specified by the input vectors.
   </td>
  </tr>
  <tr>
   <td>Divide
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The divide operation is performed on the two generic variable inputs which are of the same type. Unsupported types are: Boolean, Boolean array, String and String array.
   </td>
  </tr>
  <tr>
   <td>Duration
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The difference between the timestamp of the first and last sample.
   </td>
  </tr>
  <tr>
   <td>End time
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The timestamp of the last sample in the sequence.
   </td>
  </tr>
  <tr>
   <td>Equal
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Whether the two inputs are equal. For an array or sequence this must first mean that the number of elements is equal.
   </td>
  </tr>
  <tr>
   <td>Euler to quaternion
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The quaternion resulting from an Euler specified as a 3D vector input with the coordinates specifying yaw, pitch, roll.
   </td>
  </tr>
  <tr>
   <td>Float
   </td>
   <td>
<ol>

<li>Integer
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The float representation of the input integer.
   </td>
  </tr>
  <tr>
   <td>Float interpolation
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The interpolated value between two float values (inputs 2 and 3) for a given time (input 1).
   </td>
  </tr>
  <tr>
   <td>Gate
   </td>
   <td>
<ol>

<li>Boolean

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
Only when the boolean input is true is an update of the second input is forwarded to the output.
   </td>
  </tr>
  <tr>
   <td>Get element
   </td>
   <td>
<ol>

<li>Integer

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic value</span>
<p>
The element from the array input with the 0-based index equal to the integer input.
   </td>
  </tr>
  <tr>
   <td>Get interpolated values
   </td>
   <td>
<ol>

<li>Float array

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
An array containing the interpolated values from the sequence at the timestamps defined by the input array.
   </td>
  </tr>
  <tr>
   <td>Index of maximum
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Index</span>
<p>
The index of the maximum of the array. The function fails when the array is empty.
   </td>
  </tr>
  <tr>
   <td>Index of minimum
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Index</span>
<p>
The index of the minimum of the array. The function fails when the array is empty.
   </td>
  </tr>
  <tr>
   <td>Insert to array
   </td>
   <td>
<ol>

<li>Integer

<li>Generic value

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
A copy of the array input with the value input inserted at the 0-based index specified by the integer input.
   </td>
  </tr>
  <tr>
   <td>Integer
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Integer</span>
<p>
Integer representation of the truncated float.
   </td>
  </tr>
  <tr>
   <td>Integral
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The time integral of the float input which is calculated by determining the area under the curve of a function between two points. The integral is calculated using the trapezoidal rule.
   </td>
  </tr>
  <tr>
   <td>Intersections
   </td>
   <td>
<ol>

<li>Float

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
An array containing the timestamps of the interpolated intersections with the float value input.
   </td>
  </tr>
  <tr>
   <td>Inverse cosine
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The inverse cosine of the input float.
   </td>
  </tr>
  <tr>
   <td>Inverse quaternion
   </td>
   <td>
<ol>

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The inverse of the quaternion input.
   </td>
  </tr>
  <tr>
   <td>Inverse sine
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The inverse sine of the input float.
   </td>
  </tr>
  <tr>
   <td>Inverse tangent
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The inverse tangent of the input float.
   </td>
  </tr>
  <tr>
   <td>JSON output
   </td>
   <td>
<ol>

<li>String

<li>String

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">String</span>
<p>
A new JSON string is created which is a copy of the first string input that also contains a JSON string. A new element is added to the new JSON string using the second string input as the key for the value specified in the generic input.
   </td>
  </tr>
  <tr>
   <td>Larger
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean \
</span>Whether the first input is larger than the second. Unsupported types are: Boolean, Vector and Orientation.
   </td>
  </tr>
  <tr>
   <td>Larger or equal
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Whether the first input is larger than or equal to the second. Unsupported types are: Boolean, Vector and Orientation.
   </td>
  </tr>
  <tr>
   <td>Make quaternion
   </td>
   <td>
<ol>

<li>Float

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The quaternion resulting from a rotation in radians as specified by the float input around the vector specified by the second input.
   </td>
  </tr>
  <tr>
   <td>Make vector
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
A 3D vector is created for which the scalars are the input floats.
   </td>
  </tr>
  <tr>
   <td>Max
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic value</span>
<p>
The largest value of the two inputs. Unsupported types are: Boolean, Vector and Orientation.
   </td>
  </tr>
  <tr>
   <td>Maximum
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The maximum value in the array.
   </td>
  </tr>
  <tr>
   <td>Min
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic value</span>
<p>
The lowest value of the two inputs. Unsupported types are: Boolean, Vector and Orientation.
   </td>
  </tr>
  <tr>
   <td>Minimum
   </td>
   <td>
<ol>

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The minimum value in the array.
   </td>
  </tr>
  <tr>
   <td>Modulo
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The modulo of the input.
   </td>
  </tr>
  <tr>
   <td>Moving averager
   </td>
   <td>
<ol>

<li>Integer

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The average of the last <em>N</em> values of the float input, with <em>N</em> specified by the integer input.
   </td>
  </tr>
  <tr>
   <td>Multiply
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The result of the multiplication operation performed on the two generic inputs which are of the same type. Unsupported types are: Boolean, Boolean array,  String and String array.
   </td>
  </tr>
  <tr>
   <td>Negate
   </td>
   <td>
<ol>

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
Negates the generic input.
   </td>
  </tr>
  <tr>
   <td>Normalize
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence where the sample values are copied from the input sequence but the time <em>t</em> is scaled and shifted to start at <em>t</em> = 0 and end at <em>t</em> = 1.
   </td>
  </tr>
  <tr>
   <td>Normalize quaternion
   </td>
   <td>
<ol>

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The normalized version of the input quaternion.
   </td>
  </tr>
  <tr>
   <td>Normalize vector
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The normalized version of the input vector.
   </td>
  </tr>
  <tr>
   <td>Not
   </td>
   <td>
<ol>

<li>Boolean
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
The logical inverse of the boolean input.
   </td>
  </tr>
  <tr>
   <td>Number of elements
   </td>
   <td>
<ol>

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Integer</span>
<p>
The number of elements in the array.
   </td>
  </tr>
  <tr>
   <td>Or
   </td>
   <td>
<ol>

<li>Boolean

<li>Boolean
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
The logical OR operation between the two booleans.
   </td>
  </tr>
  <tr>
   <td>Order
   </td>
   <td>
<ol>

<li>Boolean

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
The ordered input array. The boolean indicates whether the array must be done in ascending order. Unsupported types are: Sequence array, Vector array and Orientation array.
   </td>
  </tr>
  <tr>
   <td>Pass updated
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The updated input. In the situation when both inputs are updated in the same timestamp, the first input is passed.
   </td>
  </tr>
  <tr>
   <td>Pass-through
   </td>
   <td>
<ol>

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
Simply the input when it is updated. Can be helpful to clean-up diagrams and during constructions of containers.
   </td>
  </tr>
  <tr>
   <td>Peak detector
   </td>
   <td>
<ol>

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The maximum value of the second input above the threshold (first input). Output is generated when a new maximum is set.
   </td>
  </tr>
  <tr>
   <td>Power
   </td>
   <td>
<ol>

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The value of the first float input to the power of the second.
   </td>
  </tr>
  <tr>
   <td>Quaternion
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
Orientation that is created from the 4 floats (x, y, z, w) to create a normalized quaternion.
   </td>
  </tr>
  <tr>
   <td>Quaternion angle
   </td>
   <td>
<ol>

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic</span>
<p>
The angle in radians by which to rotate around the rotation axis to get the quaternion input.
   </td>
  </tr>
  <tr>
   <td>Quaternion axis
   </td>
   <td>
<ol>

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Vector</span>
<p>
The rotation axis around which to rotate with the rotation angle to get the quaternion input.
   </td>
  </tr>
  <tr>
   <td>Quaternion interpolation
   </td>
   <td>
<ol>

<li>Float

<li>Orientation

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
The spherical linear interpolation (<a href="https://en.wikipedia.org/wiki/Slerp">SLERP</a>) value between the two timestamped orientation inputs at the timestamp specified by the float input.
   </td>
  </tr>
  <tr>
   <td>Quaternion spline
   </td>
   <td>
<ol>

<li>Float

<li>Orientation

<li>Orientation

<li>Orientation

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Orientation</span>
<p>
Interpolated quaternion between quaternions along a spherical cubic spline (using <a href="https://en.wikipedia.org/wiki/Cubic_Hermite_spline#Catmull%E2%80%93Rom_spline">Catmull-Rom</a>). The function interpolates between <em>q<sub>2</sub></em> and <em>q<sub>3</sub></em> with <em>q<sub>1</sub></em> the left endpoint of the previous interval and <em>q<sub>4</sub></em> the right endpoint of the next interval. This function smoothly interpolates between a sequence of rotations such that the quaternion and angular rate and acceleration vectors are continuous functions of time over the interpolation interval.
   </td>
  </tr>
  <tr>
   <td>Quaternion to Euler
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Vector</span>
<p>
Euler vector (yaw, pitch, roll).
   </td>
  </tr>
  <tr>
   <td>Radians to degrees
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The input float multiplied by 180 and divided by π.
   </td>
  </tr>
  <tr>
   <td>Remove from array
   </td>
   <td>
<ol>

<li>Integer

<li>Generic array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic array</span>
<p>
A copy of the input array with the element removed at the 0-based index specified by the integer input.
   </td>
  </tr>
  <tr>
   <td>Resample
   </td>
   <td>
<ol>

<li>Integer

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence created from the input sequence where the integer input specifies the new number of samples and with the new values calculated using interpolation. Note that the first and last sample of the new sequence are the same as in the input sequence.
   </td>
  </tr>
  <tr>
   <td>Rotate vector
   </td>
   <td>
<ol>

<li>Vector

<li>Orientation
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Vector</span>
<p>
The input vector rotated with the specified quaternion.
   </td>
  </tr>
  <tr>
   <td>Round
   </td>
   <td>
<ol>

<li>Float

<li>Integer
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The value of the float input rounded to the number of digits specified by the integer input.
   </td>
  </tr>
  <tr>
   <td>Scale
   </td>
   <td>
<ol>

<li>Float

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The generic input variable for which the value or all the components are multiplied by the factor specified by the float input. Unsupported types are: Boolean, Boolean array, Orientation, Orientation array, String and String array.
   </td>
  </tr>
  <tr>
   <td>Scale time
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
The sequence for which the time of the first sample is set to the value of the first float input and the time of the last sample set to the value of the second float input. The time of all the other samples in between are scaled accordingly.
   </td>
  </tr>
  <tr>
   <td>Search array
   </td>
   <td>
<ol>

<li>Float

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Integer array</span>
<p>
The output is the integer array holding the indices of the closest matches to the float input in the zero-based array.
   </td>
  </tr>
  <tr>
   <td>Select interval
   </td>
   <td>
<ol>

<li>Float

<li>Float

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence where the first sample has the timestamp of the first float value and the last has the value of the other float. The values of those samples are calculated via interpolation. All the other samples are the same as the input sequence.
   </td>
  </tr>
  <tr>
   <td>Sequence rectifier
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence with all the rectified samples of the input sequence. When two consecutive samples are of different sign, an extra sample is added with value 0 and the interpolated timestamp at which the line between the two samples intersects with 0.
   </td>
  </tr>
  <tr>
   <td>Sequence timestamps
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
An array containing the timestamps of all the samples of the input sequence.
   </td>
  </tr>
  <tr>
   <td>Sequence values
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
An array containing the values of all the samples of the input sequence.
   </td>
  </tr>
  <tr>
   <td>Sequencer
   </td>
   <td>
<ol>

<li>Float

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
An internal sequence is created which stores all the updates of the second float value. The maximum allowed duration of this sequence is set to the value of the first float input. This means that when a new sample is added which would cause the sequence to become too long, all the oldest samples are deleted that fall outside the interval and a new first sample is added to the sequence with a timestamp equal to that of the last sample minus the duration and a value calculated via interpolation.
   </td>
  </tr>
  <tr>
   <td>Shift elements
   </td>
   <td>
<ol>

<li>Float

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
A new array where the float value is added to each element of the array.
   </td>
  </tr>
  <tr>
   <td>Shift time
   </td>
   <td>
<ol>

<li>Float

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence which is a copy from the input sequence but with the value of the float input added to each timestamp.
   </td>
  </tr>
  <tr>
   <td>Sine
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The sine of the float input.
   </td>
  </tr>
  <tr>
   <td>Smaller
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Whether the first input is smaller than the second input. Unsupported types are: Boolean, Vector and Orientation.
   </td>
  </tr>
  <tr>
   <td>Smaller or equal
   </td>
   <td>
<ol>

<li>Generic value

<li>Generic value
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Whether the first input is smaller than or equal to the second input. Only implemented for Float and Integer. Unsupported types are: Boolean, Vector, and Orientation.
   </td>
  </tr>
  <tr>
   <td>Start time
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The timestamp of the first sample in the sequence.
   </td>
  </tr>
  <tr>
   <td>Subtract
   </td>
   <td>
<ol>

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
The result of the subtraction operation performed on the two generic inputs which are of the same type. Unsupported types are: Boolean, Boolean array, String, String array.
   </td>
  </tr>
  <tr>
   <td>Switch
   </td>
   <td>
<ol>

<li>Boolean

<li>Generic variable

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic variable</span>
<p>
When the boolean input is <em>true</em>, the first one of the generic inputs is forwarded when updated, otherwise the second generic input is forwarded when updated.
   </td>
  </tr>
  <tr>
   <td>Tangent
   </td>
   <td>
<ol>

<li>Float
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The tangent of the float input.
   </td>
  </tr>
  <tr>
   <td>Time derivative
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence containing the time derivative of the input sequence.
   </td>
  </tr>
  <tr>
   <td>Time integral
   </td>
   <td>
<ol>

<li>Sequence
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Sequence</span>
<p>
A new sequence containing the time integral of the input sequence, i.e. the area ‘under the curve’.
   </td>
  </tr>
  <tr>
   <td>Timestamp
   </td>
   <td>
<ol>

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The timestamp at which the input value was updated.
   </td>
  </tr>
  <tr>
   <td>Toggled
   </td>
   <td>
<ol>

<li>Boolean
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Whether or not the boolean input changed its value (<em>true</em> to <em>false</em> or vice versa). Note that the first time the boolean input is updated is used to set the initial value and will not result in an output.
   </td>
  </tr>
  <tr>
   <td>Trigger
   </td>
   <td>
<ol>

<li>Boolean

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Generic</span>
<p>
When the boolean input is updated to true, the other input is forwarded as an update irrespective of whether it was updated or not.
   </td>
  </tr>
  <tr>
   <td>Trim
   </td>
   <td>
<ol>

<li>Integer

<li>Integer

<li>Float array
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float array</span>
<p>
A new array that is a subset of the input array containing the elements with a  0-based index larger or equal to the first integer input and smaller or equal to the second integer input.
   </td>
  </tr>
  <tr>
   <td>Update counter
   </td>
   <td>
<ol>

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Integer</span>
<p>
The number of times the input was updated.
   </td>
  </tr>
  <tr>
   <td>Updated
   </td>
   <td>
<ol>

<li>Generic variable
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
Updates to <em>true</em> when the input is updated. Note that this does not mean that actual value changed.
   </td>
  </tr>
  <tr>
   <td>Vector angle
   </td>
   <td>
<ol>

<li>Vector

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The angle in radians between the two input vectors.
   </td>
  </tr>
  <tr>
   <td>Vector cross product
   </td>
   <td>
<ol>

<li>Vector

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Vector</span>
<p>
The cross-product of the two input vectors.
   </td>
  </tr>
  <tr>
   <td>Vector dot product
   </td>
   <td>
<ol>

<li>Vector

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The dot-product of the two input vectors.
   </td>
  </tr>
  <tr>
   <td>Vector length
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The length of the vector.
   </td>
  </tr>
  <tr>
   <td>Vector x-coordinate
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The x-coordinate of the vector.
   </td>
  </tr>
  <tr>
   <td>Vector y-coordinate
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The x-coordinate of the vector.
   </td>
  </tr>
  <tr>
   <td>Vector z-coordinate
   </td>
   <td>
<ol>

<li>Vector
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Float</span>
<p>
The x-coordinate of the vector.
   </td>
  </tr>
  <tr>
   <td>Xor
   </td>
   <td>
<ol>

<li>Boolean

<li>Boolean
</li>
</ol>
   </td>
   <td><span style="text-decoration:underline;">Boolean</span>
<p>
The logical XOR operation between the two booleans.
   </td>
  </tr>
</table>

