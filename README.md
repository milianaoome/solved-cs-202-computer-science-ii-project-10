Download Link: https://assignmentchef.com/product/solved-cs-202-computer-science-ii-project-10
<br>



<strong>  </strong>




<strong>Objectives:  </strong>The main objectives of this project are to test your ability to create and use stackbased dynamic data structures, and generalize your code using <u>templates</u>. A review of your knowledge to manipulate dynamic memory, classes, pointers and iostream to all extents, is also included. You may from now on freely use <strong>square bracket</strong>-indexing, <strong>pointers</strong>, <strong>references</strong>, all <strong>operators</strong>, the <strong>&lt;cstring&gt;</strong> library, and the <strong>std::string</strong> type as you deem proper.




<strong>Description: </strong>

For this project you will create a <u>templated</u> Stack class, with an Array-based and a Node-based variant. A Stack is a Last In First Out (LIFO) data structure. A Stack exclusively inserts data at the top (<strong>push</strong>) and removes data from the top (<strong>pop</strong>) as well. The Stack’s <strong>top</strong> data member points to the last inserted element (the most recent one).




The following provided specifications refer to Stacks that work with DataType class objects, similarly to the previous project. For the this Project’s requirements, you will have to make the necessary modifications so that your ArrayStack and NodeStack and all their functionalities are generalized <u>templated</u> classes.




<strong><u>Templated</u> Array-based Stack: </strong>

The following header file excerpt is used to explain the required specifications for the class. This only refers an Array-based Stack that holds elements of type class DataType. You will additionally have to <u>template</u> this class, and provide the necessary header file with the necessary declarations and implementations:

<strong>const</strong> <strong>size_t</strong> <strong>MAX_STACKSIZE</strong><strong> = 1000; </strong>

<strong> </strong>

<strong>class</strong> <strong>ArrayStack</strong><strong>{   </strong><strong>friend</strong> <strong>std::ostream&amp;</strong> <strong>operator&lt;&lt;</strong><strong>(</strong><strong>std::ostream&amp;</strong><strong> os,  </strong><strong>     //(i)</strong><strong>                </strong><strong>                  const ArrayStack&amp;</strong><strong> arrayStack);    </strong><strong>public: </strong>

<strong>    </strong><strong>ArrayStack();</strong><strong>                                              </strong><strong>//(1) </strong>

<table width="629">

 <tbody>

  <tr>

   <td width="576"><strong>    </strong><strong>ArrayStack</strong><strong>(</strong><strong>size_t</strong><strong> count, </strong><strong>const DataType&amp; </strong><strong>value);         </strong></td>

   <td width="53"><strong>//(2)</strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    </strong><strong>ArrayStack</strong><strong>(</strong><strong>const ArrayStack&amp;</strong><strong> other);                    </strong></td>

   <td width="53"><strong>//(3) </strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    </strong><strong>~ArrayStack</strong><strong>();                                        </strong><strong> </strong></td>

   <td width="53"><strong>//(4)</strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    ArrayStack&amp;</strong> <strong>operator= </strong><strong>(</strong><strong>const ArrayStack&amp; </strong><strong>rhs);         </strong></td>

   <td width="53"><strong>//(5) </strong></td>

  </tr>

 </tbody>

</table>

<strong>     </strong>

<table width="633">

 <tbody>

  <tr>

   <td width="384"><strong>    </strong><strong>DataType&amp;</strong> <strong>top</strong><strong>();                  </strong></td>

   <td colspan="3" width="249"><strong>                </strong><strong>    //(6a) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>const DataType&amp;</strong><strong> top</strong><strong>() </strong><strong>const</strong><strong>;       </strong><strong>    </strong></td>

   <td colspan="3" width="249"><strong>                </strong><strong>    //(6b)</strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void</strong> <strong>push</strong><strong>(</strong><strong>const DataType&amp;</strong><strong> value);  </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          //(7) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void </strong><strong>pop</strong><strong>();                        </strong><strong>                 </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          </strong><strong>//(8) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>size_t</strong> <strong>size</strong><strong>() </strong><strong>const</strong><strong>;               </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          //(9) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>bool</strong> <strong>empty</strong><strong>() </strong><strong>const</strong><strong>;               </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>   </strong><strong>    //(10) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    bool</strong> <strong>full</strong><strong>() </strong><strong>const</strong><strong>;                </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>   </strong><strong>    //(11) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void</strong> <strong>clear</strong><strong>();                     </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>     </strong><strong>    //(12)</strong><strong>  </strong></td>

  </tr>

  <tr>

   <td colspan="2" width="432"><strong>    </strong><strong>void </strong><strong>serialize</strong><strong>(</strong><strong>std::ostream&amp;</strong><strong> os) </strong><strong>const</strong><strong>;  </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>        </strong><strong> //(13) </strong><strong> </strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>  private: </strong>

<h1>    DataType m_container[MAX_STACKSIZE];     size_t m_top; };</h1>

The <strong>ArrayStack </strong>Class will contain the following<strong> private </strong>data members:

<ul>

 <li><strong>m_container,</strong> the array that holds the data. Note: Here it is given to hold DataType class objects and have a maximum size of MAX_STACKSIZE. For this Project’s requirements, <u>both of these parameters</u> will have to be determined via <u>Template Parameters</u>.</li>

 <li><strong>m_top,</strong> a size_t, with the respective m_container index of the top element of the ArrayStack. <em>Note</em>: This should never exceed MAX_STACKSIZE-1.</li>

</ul>

,will have the following<strong> public </strong>member functions:

<ul>

 <li><strong>(1) Default Constructor</strong> – will instantiate a new ArrayStack object with no valid data.</li>

 <li><strong>(2) Parametrized Constructor </strong>– will instantiate a new ArrayStack object, which will hold size_t count number of elements in total, all of them initialized to be equal to the parameter value.</li>

 <li><strong>(3) Copy Constructor</strong> – will instantiate a new ArrayStack object which will be a separate copy of the data of the <strong>other </strong>ArrayStack object which is getting copied. <em>Note</em>: Consider whether you actually need to implement this.</li>

 <li><strong>(4) Destructor </strong>– will destroy the instance of the ArrayStack object. <em>Note</em>: Consider whether you actually need to implement this.</li>

 <li><strong>(5) operator= </strong>will assign a new value to the calling ArrayStack object, which will be an exact copy of the rhs object passed as a parameter. Returns a reference to the calling object to be used for cascading operator= as per standard practice. <em>Note</em>: Consider whether you actually need to implement this.</li>

 <li><strong>(6a,6b) top </strong>returns a Reference to the top element of the stack. <em>Note</em>: Since it returns a Reference, before calling this method the user must ensure that the stack is not empty.</li>

 <li><strong>(7) push </strong>inserts at the top of the stack an element of the given value. <em>Note</em>: Since m_top can never exceed MAX_STACKSIZE-1, checking if the stack is full prior to pushing a new element makes sense.</li>

 <li><strong>(8) pop </strong>removes the top element of the stack. <em>Note</em>: Since m_top is an unsigned value, checking if the stack is empty prior to popping an element makes sense.</li>

 <li><strong>(9) size </strong>will return the current size of the ArrayStack.</li>

 <li><strong>(10) empty </strong>will return a bool, true if the ArrayStack is empty.</li>

 <li><strong>(11) full </strong>will return a bool, true if the ArrayStack is full.</li>

 <li><strong>(12) clear </strong>performs the necessary actions, so that after its call the ArrayStack will be semantically considered empty.</li>

 <li><strong>(13) serialize </strong>outputs to the parameter ostream os the complete content of the calling ArrayStack object (ordered from top to bottom).</li>

</ul>

as well as a non-member overload for:

<ul>

 <li><strong>(i) operator&lt;&lt; </strong>will output (to terminal or file) the complete content of the arrayStack object passed as a parameter.</li>

</ul>

























<strong><u>Templated</u> Node-based Stack: </strong>

The following header file excerpt is used to explain the required specifications for the class. This only refers a Node-based Stack that holds elements of type class DataType. You will additionally have to <u>template</u> this class, and provide the necessary header file with the necessary declarations and implementations:

<strong>class</strong> <strong>NodeStack</strong><strong>{   </strong><strong>friend</strong> <strong>std::ostream&amp;</strong> <strong>operator&lt;&lt;</strong><strong>(</strong><strong>std::ostream&amp;</strong><strong> os,  </strong><strong>     //(i)</strong><strong>    </strong><strong>                  const NodeStack&amp;</strong><strong> nodeStack);    </strong><strong>public: </strong>

<table width="629">

 <tbody>

  <tr>

   <td width="576"><strong>    </strong><strong>NodeStack();</strong><strong>                                          </strong></td>

   <td width="53"><strong>//(1) </strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    </strong><strong>NodeStack</strong><strong>(</strong><strong>size_t</strong><strong> count, </strong><strong>const DataType&amp; </strong><strong>value);          </strong></td>

   <td width="53"><strong>//(2)</strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    </strong><strong>NodeStack</strong><strong>(</strong><strong>const NodeStack&amp;</strong><strong> other);                       </strong></td>

   <td width="53"><strong>//(3) </strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    </strong><strong>~NodeStack</strong><strong>();                                         </strong><strong> </strong></td>

   <td width="53"><strong>//(4)</strong></td>

  </tr>

  <tr>

   <td width="576"><strong>    NodeStack&amp;</strong> <strong>operator= </strong><strong>(</strong><strong>const NodeStack&amp; </strong><strong>rhs);             </strong></td>

   <td width="53"><strong>//(5) </strong></td>

  </tr>

 </tbody>

</table>

<strong>     </strong>

<table width="633">

 <tbody>

  <tr>

   <td width="384"><strong>    </strong><strong>DataType&amp;</strong> <strong>top</strong><strong>();                  </strong></td>

   <td colspan="3" width="249"><strong>                </strong><strong>    //(6a) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>const DataType&amp;</strong><strong> top</strong><strong>() </strong><strong>const</strong><strong>;       </strong><strong>    </strong></td>

   <td colspan="3" width="249"><strong>                </strong><strong>    //(6b)</strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void</strong> <strong>push</strong><strong>(</strong><strong>const DataType&amp;</strong><strong> value);  </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          //(7) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void </strong><strong>pop</strong><strong>();                        </strong><strong>                 </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          </strong><strong>//(8) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>size_t</strong> <strong>size</strong><strong>() </strong><strong>const</strong><strong>;               </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>          //(9) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>bool</strong> <strong>empty</strong><strong>() </strong><strong>const</strong><strong>;               </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>   </strong><strong>    //(10) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    bool</strong> <strong>full</strong><strong>() </strong><strong>const</strong><strong>;                </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>   </strong><strong>    //(11) </strong></td>

  </tr>

  <tr>

   <td width="384"><strong>    </strong><strong>void</strong> <strong>clear</strong><strong>();                     </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>     </strong><strong>    //(12)</strong><strong>  </strong></td>

  </tr>

  <tr>

   <td colspan="2" width="432"><strong>    </strong><strong>void </strong><strong>serialize</strong><strong>(</strong><strong>std::ostream&amp;</strong><strong> os) </strong><strong>const</strong><strong>;  </strong></td>

   <td width="48"><strong> </strong></td>

   <td width="153"><strong>        </strong><strong> //(13) </strong><strong> </strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>  private: </strong>

<h1>    Node* m_top; };</h1>

The following references a Node class that holds elements of type class DataType. You will also have to <u>template</u> this class as well, and preferably put the necessary declarations and implementations in the same header file as the NodeStack templated class: <strong>class</strong> <strong>Node</strong><strong>{ </strong>

<strong>  </strong><strong>friend</strong> <strong>class</strong> <strong>NodeStack</strong><strong>;  </strong>

<strong> </strong>

<strong>  </strong><strong>public: </strong>

<h1>    Node();</h1>

<strong>    </strong><strong>Node</strong><strong>(</strong><strong>const DataType&amp;</strong><strong> data, </strong><strong>Node*</strong><strong> next = </strong><strong>NULL</strong><strong>); </strong>

<strong> </strong>

<strong>    </strong><strong>DataType&amp; </strong><strong>GetData</strong><strong>; </strong>

<strong>    </strong><strong>const DataType&amp;</strong> <strong>GetData</strong><strong>() </strong><strong>const</strong><strong>; </strong>

<strong>                                                                 </strong><strong>  private: </strong>

<h1>    Node* m_next     DataType m_data;                         };</h1>




The <strong>NodeStack </strong>Class will contain the following<strong> private </strong>data members:

<ul>

 <li><strong>m_top,</strong> a <u>templated</u> (you need to <u>template</u> this) Node Pointer type, pointing to the top (last) element of the Stack.</li>

</ul>

,will have the following<strong> public </strong>member functions:

<ul>

 <li><strong>(1) Default Constructor</strong> – will instantiate a new NodeStack object with no elements (Nodes).</li>

 <li><strong>(2) Parametrized Constructor </strong>– will instantiate a new NodeStack object, which will be dynamically allocated at instantiation to hold size_t count number of elements (Nodes), all of them initialized to be equal to the parameter value.</li>

 <li><strong>(3) Copy Constructor</strong> – will instantiate a new NodeStack object which will be a separate copy of the data of the <strong>other </strong>NodeStack object which is getting copied. <em>Note</em>: Consider why now you do need to implement this.</li>

 <li><strong>(4) Destructor </strong>– will destroy the instance of the NodeStack object. <em>Note</em>: Consider why now you do need to implement this.</li>

 <li><strong>(5) operator= </strong>will assign a new value to the calling NodeStack object, which will be an exact copy of the rhs object passed as a parameter. Returns a reference to the calling object to be used for cascading operator= as per standard practice. <em>Note</em>: Consider why now you do need to implement this.</li>

 <li><strong>(6a,6b) top </strong>returns a Reference to the top element of the stack. <em>Note</em>: Since it returns a Reference, before calling this method the user must ensure that the stack is not empty.</li>

 <li><strong>(7) push </strong>inserts at the top of the stack an element of the given value. <em>Note</em>: No imposed maximum size limitations exist for the Node-based stack variant.</li>

 <li><strong>(8) pop </strong>removes the top element of the stack. <em>Note</em>: Checking if the stack is empty prior to popping an element still makes sense.</li>

 <li><strong>(9) size </strong>will return the current size of the NodeStack.</li>

 <li><strong>(10) empty </strong>will return a bool, true if the NodeStack is empty.</li>

 <li><strong>(11) full </strong>will return a bool, true if the NodeStack is full. <em>Note</em>: Kept for compatibility, should always return false.</li>

 <li><strong>(12) clear </strong>performs the necessary actions, so that after its call the NodeStack will become empty.</li>

 <li><strong>(13) serialize </strong>outputs to the parameter ostream os the complete content of the calling NodeStack object (ordered from top to bottom).</li>

</ul>

as well as a non-member overload for:

<ul>

 <li><strong>(i) operator&lt;&lt; </strong>will output (to terminal or file) the complete content of the nodeStack object passed as a parameter.</li>

</ul>




You will create the necessary ArrayStack.h and NodeStack.h files that contain the <strong><u>templated</u> class declarations and implementations</strong>. You should also create a source file proj10.cpp which will be a test driver for your classes.

<strong>Templates are special! Do not try to separate declaration &amp; implementation in header and source files as you were used to doing. Follow the guidelines about a single header file ArrayStack.h and a single NodeStack.h, each holding both declarations and respective implementations. </strong>

<strong>Suggestion(s): First try to implement the two Stack variants as non-templated classes (will closely resemble a simplified version of Project_9). Create a test driver for your code and verify that it works. Then move on to write template-based generic versions of your classes. </strong>




<strong>The completed project should have the following properties: </strong> Ø Written, compiled and tested using Linux.

<ul>

 <li>It must compile successfully on the department machines using Makefile(s), which will be invoking the g++ compiler. Instructions how to remotely connect to department machines are included in the Projects folder in WebCampus.</li>

 <li>The code must be commented and indented properly.</li>

</ul>

Header comments are required on all files and recommended for the rest of the program. Descriptions of functions commented properly.

<ul>

 <li>A one page (minimum) typed sheet documenting your code. This should include the overall purpose of the program, your design, problems (if any), and any changes you would make given more time.</li>

</ul>

<strong> </strong>

<strong>Turn in:</strong> Compressed Header &amp; Source files, Makefile(s), and project documentation.


