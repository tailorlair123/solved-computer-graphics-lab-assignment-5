Download Link: https://assignmentchef.com/product/solved-computer-graphics-lab-assignment-5
<br>
<strong>Computer Graphics, Lab Assignment 5 </strong>

+ LabAssignment2/

+ 1/

<ul>

 <li>py</li>

</ul>

+ 2/

<ul>

 <li>py</li>

</ul>

+ 3/

<ul>

 <li>py</li>

</ul>




<ul>

 <li>The submission time is determined not when the commit is made but when the git push is made.</li>

</ul>




<ol>

 <li>Write down a Python program to draw a transformed triangle and its local frame in a 3D space. A. Set the window title to <strong>your student ID</strong> and the window size to (480,480).

  <ol>

   <li>Use the following drawFrame() and drawTriangle() to draw the frame and triangle:</li>

  </ol></li>

</ol>

<table width="555">

 <tbody>

  <tr>

   <td width="555">

    <table width="267">

     <tbody>

      <tr>

       <td colspan="2" width="128"><strong>def</strong> drawFrame<strong>():</strong></td>

       <td colspan="3" width="139"> </td>

      </tr>

      <tr>

       <td colspan="3" width="163">    glBegin<strong>(</strong>GL_LINES<strong>)</strong></td>

       <td colspan="2" width="104"> </td>

      </tr>

      <tr>

       <td colspan="4" width="195">    glColor3ub<strong>(</strong>255<strong>,</strong> 0<strong>,</strong> 0<strong>)</strong></td>

       <td width="72"> </td>

      </tr>

      <tr>

       <td colspan="5" width="267">    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>])) </strong>    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>1.<strong>,</strong>0.<strong>]))</strong></td>

      </tr>

      <tr>

       <td colspan="4" width="195">    glColor3ub<strong>(</strong>0<strong>,</strong> 255<strong>,</strong> 0<strong>)</strong></td>

       <td width="72"> </td>

      </tr>

      <tr>

       <td colspan="5" width="267">    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>])) </strong>    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>1.<strong>]))</strong></td>

      </tr>

      <tr>

       <td width="83">    glEnd<strong>()</strong></td>

       <td colspan="4" width="184"> </td>

      </tr>

      <tr>

       <td width="83"></td>

       <td width="45"></td>

       <td width="35"></td>

       <td width="32"></td>

       <td width="72"></td>

      </tr>

     </tbody>

    </table>


    <table width="267">

     <tbody>

      <tr>

       <td colspan="2" width="152"><strong>def</strong> drawTriangle<strong>():</strong></td>

       <td colspan="2" width="115"> </td>

      </tr>

      <tr>

       <td colspan="3" width="195">    glBegin<strong>(</strong>GL_TRIANGLES<strong>)</strong></td>

       <td width="72"> </td>

      </tr>

      <tr>

       <td colspan="4" width="267">    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>.5<strong>])) </strong>    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>])) </strong>    glVertex2fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>.5<strong>,</strong>0.<strong>]))</strong></td>

      </tr>

      <tr>

       <td width="83">    glEnd<strong>()</strong></td>

       <td colspan="3" width="184"> </td>

      </tr>

      <tr>

       <td width="83"></td>

       <td width="69"></td>

       <td width="43"></td>

       <td width="72"></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<ol>

 <li>First draw an untransformed white triangle and a global frame.</li>

 <li>Then draw a transformed blue triangle and its local frame. The triangle should be first rotated by 30 degrees and then translated by (0.6, 0, 0) w.r.t. the global frame. E. Expected result:</li>

 <li></li>

 <li>Files to submit: A Python source file (Name the file whatever you want (in English). Extension should be .py)</li>

</ol>




<ol start="2">

 <li>Write down a Python program to draw a transformed triangle in a 3D space.

  <ol>

   <li>Set the window title to <strong>your student ID</strong> and the window size to (480,480).</li>

   <li>Use the following code snippet:</li>

  </ol></li>

</ol>

gCamAng <strong>=</strong> 0

gComposedM <strong>=</strong> np<strong>.</strong>identity<strong>(</strong>4<strong>)</strong>

<strong>def</strong> render<strong>(</strong>M<strong>,</strong> camAng<strong>):</strong>

# enable depth test (we’ll see details later)     glClear<strong>(</strong>GL_COLOR_BUFFER_BIT <strong>|</strong> GL_DEPTH_BUFFER_BIT<strong>)</strong>     glEnable<strong>(</strong>GL_DEPTH_TEST<strong>)</strong>




glLoadIdentity<strong>()</strong>




# use orthogonal projection (we’ll see details later)     glOrtho<strong>(-</strong>1<strong>,</strong>1<strong>,</strong> <strong>–</strong>1<strong>,</strong>1<strong>,</strong> <strong>–</strong>1<strong>,</strong>1<strong>)</strong>




# rotate “camera” position to see this 3D space better (we’ll see details later)

gluLookAt<strong>(</strong>.1<strong>*</strong>np<strong>.</strong>sin<strong>(</strong>camAng<strong>),</strong>.1<strong>,</strong> .1<strong>*</strong>np<strong>.</strong>cos<strong>(</strong>camAng<strong>),</strong> 0<strong>,</strong>0<strong>,</strong>0<strong>,</strong> 0<strong>,</strong>1<strong>,</strong>0<strong>)</strong>

# draw coordinate: x in red, y in green, z in blue     glBegin<strong>(</strong>GL_LINES<strong>)</strong>     glColor3ub<strong>(</strong>255<strong>,</strong> 0<strong>,</strong> 0<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>1.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glColor3ub<strong>(</strong>0<strong>,</strong> 255<strong>,</strong> 0<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>1.<strong>,</strong>0.<strong>]))</strong>     glColor3ub<strong>(</strong>0<strong>,</strong> 0<strong>,</strong> 255<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>1.<strong>]))</strong>     glEnd<strong>()</strong>




# draw triangle     glBegin<strong>(</strong>GL_TRIANGLES<strong>)</strong>     glColor3ub<strong>(</strong>255<strong>,</strong> 255<strong>,</strong> 255<strong>)</strong>     glVertex3fv<strong>((</strong>M @ np<strong>.</strong>array<strong>([</strong>.0<strong>,</strong>.5<strong>,</strong>0.<strong>,</strong>1.<strong>]))[:-</strong>1<strong>])</strong>     glVertex3fv<strong>((</strong>M @ np<strong>.</strong>array<strong>([</strong>.0<strong>,</strong>.0<strong>,</strong>0.<strong>,</strong>1.<strong>]))[:-</strong>1<strong>])</strong>     glVertex3fv<strong>((</strong>M @ np<strong>.</strong>array<strong>([</strong>.5<strong>,</strong>.0<strong>,</strong>0.<strong>,</strong>1.<strong>]))[:-</strong>1<strong>])</strong>     glEnd<strong>()</strong>

<strong>def</strong> key_callback<strong>(</strong>window<strong>,</strong> key<strong>,</strong> scancode<strong>,</strong> action<strong>,</strong> mods<strong>):</strong>

<strong>global</strong> gCamAng<strong>,</strong> gComposedM     <strong>if</strong> action<strong>==</strong>glfw<strong>.</strong>PRESS <strong>or</strong> action<strong>==</strong>glfw<strong>.</strong>REPEAT<strong>:</strong>

<strong>if</strong> key<strong>==</strong>glfw<strong>.</strong>KEY_1<strong>:</strong>

gCamAng <strong>+=</strong> np<strong>.</strong>radians<strong>(-</strong>10<strong>)</strong>         <strong>elif</strong> key<strong>==</strong>glfw<strong>.</strong>KEY_3<strong>:</strong>             gCamAng <strong>+=</strong> np<strong>.</strong>radians<strong>(</strong>10<strong>)</strong>




<ol>

 <li>If you press or repeat a key, the triangle should be transformed as shown in the Table.</li>

</ol>

Note that key 1 and 3 are already implemented in the above code snippet.

<table width="434">

 <tbody>

  <tr>

   <td colspan="3" width="434"><strong>Key</strong> <strong>Transformation</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>Q       </strong>Translate by -0.1 in  x direction <strong>w.r.t global coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>E       </strong>Translate by 0.1 in x direction <strong>w.r.t global coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>A       </strong>Rotate about y axis by -10 degrees <strong>w.r.t local coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>D       </strong>Rotate about y axis by +10 degrees <strong>w.r.t local coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>W      </strong>Rotate about x axis by -10 degrees <strong>w.r.t local coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td colspan="3" width="434"><strong>S       </strong>Rotate about x axis by +10 degrees <strong>w.r.t local coordinate</strong></td>

   <td width="0"> </td>

  </tr>

  <tr>

   <td width="0"> </td>

   <td width="45"><strong>1 </strong></td>

   <td colspan="2" width="389">Rotate camera -10 degree</td>

  </tr>

  <tr>

   <td width="0"> </td>

   <td width="45"><strong>3 </strong></td>

   <td colspan="2" width="389">Rotate camera 10 degree</td>

  </tr>

  <tr>

   <td width="0"></td>

   <td width="45"></td>

   <td width="388"></td>

   <td width="0"></td>

  </tr>

 </tbody>

</table>

<ol>

 <li>Transformations should be accumulated (composed with previous one).</li>

 <li>You’ll need two global variables to store current accumulated transformation and current camera angle.</li>

 <li>Files to submit: A Python source file (Name the file whatever you want (in English). Extension should be .py)</li>

</ol>





