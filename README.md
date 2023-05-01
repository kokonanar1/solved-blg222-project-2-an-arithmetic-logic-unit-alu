Download Link: https://assignmentchef.com/product/solved-blg222-project-2-an-arithmetic-logic-unit-alu
<br>
<strong>(Part-1)</strong> Design an Arithmetic Logic Unit (ALU) that has two 8-bit inputs and an 8-bit output. The ALU is shown on the left side of  Figure 1. The ALU functions and the flags that will be updated (i.e., <strong>–</strong> means that the flag will not be affected and <strong>√</strong> means that the flag changes based on the OutALU) are given on the right side of Figure 1:

<ul>

 <li><strong>FunSel</strong> selects the function of the ALU.</li>

 <li><strong>OutALU </strong>shows the result of the operation that is selected by <strong>FunSel</strong> and applied on A and/or B inputs.</li>

 <li><strong>Z (zero) </strong>bit is set if <strong>OutALU</strong> is zero (e.g., <strong>NOT B </strong>is zero).</li>

 <li><strong>C (carry) </strong>bit is set if <strong>OutALU</strong> sets the carry (e.g.,<strong> LSL A </strong>produces carry).</li>

 <li><strong>N (negative) </strong>bit is set if the ALU operation generates a negative result (e.g., <strong>A–B </strong>results in a negative number).</li>

 <li><strong>O (overflow) </strong>bit is set if an overflow occurs (e.g., <strong>A+B</strong> results in an overflow)<strong>.</strong></li>

 <li>Note that <strong>Z|C|N|O</strong> flags are stored in a <strong>register! </strong></li>

</ul>

<strong> </strong>

<table width="296">

 <tbody>

  <tr>

   <td width="55">FunSel</td>

   <td width="98">OutALU</td>

   <td width="48">Z</td>

   <td width="32">C</td>

   <td width="23">N</td>

   <td width="39">O</td>

  </tr>

  <tr>

   <td width="55">00000001</td>

   <td width="98">AB</td>

   <td width="48">  </td>

   <td width="32">  </td>

   <td width="23">  </td>

   <td width="39">  </td>

  </tr>

  <tr>

   <td width="55">00100011</td>

   <td width="98">NOT A NOT B</td>

   <td width="48">  </td>

   <td width="32">  </td>

   <td width="23">  </td>

   <td width="39">  </td>

  </tr>

  <tr>

   <td width="55">01000101 0110</td>

   <td width="98">A + BA + B + CarryA – B</td>

   <td width="48">  </td>

   <td width="32">  </td>

   <td width="23">  </td>

   <td width="39">  </td>

  </tr>

  <tr>

   <td width="55">01111000 1001</td>

   <td width="98">A AND BA OR BA XOR B</td>

   <td width="48">  </td>

   <td width="32">   </td>

   <td width="23">  </td>

   <td width="39">   </td>

  </tr>

  <tr>

   <td width="55">1010 101111001101 11101111</td>

   <td width="98">LSL ALSR AASL AASR A CSL ACSR A</td>

   <td width="48">    </td>

   <td width="32">     </td>

   <td width="23">      </td>

   <td width="39">      </td>

  </tr>

 </tbody>

</table>

OutALU                      Register

Figure 1: The ALU (Left) and its characteristic table (Right)

<strong>(C</strong>ircular | <strong>A</strong>rithmetic | <strong>L</strong>ogical) <strong>S</strong>hift (<strong>L</strong>eft | <strong>R</strong>ight) operations are depicted in Figure 2, <em>Figure 3</em><em>, and </em><em>Figure 4</em>.

<em>Figure 2: Circular Shift Operations </em>

<em>Figure 3: Logical Shift Operations </em>

<em>Figure 4: Arithmetic Shift Operations </em>

<strong> (Part-2) </strong>Implement the organization in Figure 5. Please note that, <strong>the whole system uses  the same single clock. </strong>

IR (0-7)

IR (8-15)

<table width="573">

 <tbody>

  <tr>

   <td width="213">


    <table width="178">

     <tbody>

      <tr>

       <td width="57">MuxASel</td>

       <td width="121">MuxAOut</td>

      </tr>

      <tr>

       <td width="57">00011011</td>

       <td width="121">IROut (0-7)Memory OutputAddress Register OutCOutALU</td>

      </tr>

     </tbody>

    </table></td>

   <td width="197">


    <table width="132">

     <tbody>

      <tr>

       <td width="57">MuxBSel</td>

       <td width="76">MuxBOut</td>

      </tr>

      <tr>

       <td width="57">00011011</td>

       <td width="76">ɸIROut (0-7)Memory OutputOutALU</td>

      </tr>

     </tbody>

    </table></td>

   <td width="163">


    <table width="132">

     <tbody>

      <tr>

       <td width="57">MuxCSel</td>

       <td width="76">MuxCOut</td>

      </tr>

      <tr>

       <td width="57">01</td>

       <td width="76">MuxAOutOutA</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<h1>Figure 5: ALU System</h1>

<strong> </strong>


