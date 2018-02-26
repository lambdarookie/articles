# Notes On Java

![Java Duke](duke.png)

## Notes

+ 10 February 2018 - [Hello, world.](#hello-world)
+ 11 February 2018 - [The Ultimate Java Access Modifiers Table](#the-ultimate-java-access-modifiers-table)


## Hello, world.
> 10 February 2018

Hello, world. My name is Lucas. Even though I programmed in Java for quite some time now, I oftentimes still feel like a rookie. There is just so much to learn about the Java language and its ecosystem! And because I like to share what I learn, I eventually decided to publish my notes here. I hope you will find the content useful. Also, feedback is very welcome!

## The Ultimate Java Access Modifiers Table
> 11 February 2018

Ever since I got introduced to the Java programming language during the first semester of my university studies, I felt like I needed to brush up my understanding of Java's access modifiers. I never quite understood how access modifiers of classes, interfaces, etc. affected those of their fields, methods, etc. Years later, while preparing for the OCA Java SE 8 Programmer I Certification exam (which I keep telling myself I will take before 2030), I stumbled upon this issue again. I noticed that none of the tables that I looked at online covered the relationship between the access modifiers of top-level entities with those of their fields and methods, so I decided to create my own that does just that. It shows whether or not a field (or method, etc.) can be accessed, and how. If a field can be accessed, then either by inheritance (using `this.theField`) or via reference (using `theObject.theField`). Also, note that top-level entities can neither be `protected` nor `private`.

<table>
  <tr>
    <th rowspan=3 colspan=3>
      The Ultimate Java Access Modifiers Table
    </th>
    <th colspan=4>Class, interface, etc.</th>
  </tr>
  <tr>
    <th colspan=2><code>public</code></th>
    <th colspan=2>default</th>
  </tr>
  <tr>
  	<th>Same package</th>
  	<th>Separate package</th>
  	<th>Same package</th>
  	<th>Separate package</th>
  </tr>
  <tr>
    <th rowspan=8>Field, method, etc.</th>
    <th rowspan=2><code>public</code></th>
    <th>Derived class</th>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th>Unrelated class</th>
  	<td>Reference</td>
  	<td>Reference</td>
  	<td>Reference</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th rowspan=2><code>protected</code></th>
    <th>Derived class</th>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>
  	  <b>Inheritance only!</b>
  	</td>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th>Unrelated class</th>
  	<td>Reference</td>
  	<td>Field is not accessible.</td>
  	<td>Reference</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th rowspan=2>default</th>
    <th>Derived class</th>
  	<td>
  	  Inheritance
  	  Reference
  	</td>
  	<td>Field is not accessible.</td>
  	<td>
  	  Inheritance
  	  Reference
    </td>
    <td>Class is not visible.</td>
  </tr>
  <tr>
    <th>Unrelated class</th>
  	<td>Reference</td>
  	<td>Field is not accessible.</td>
  	<td>Reference</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th rowspan=3><code>private</code></th>
    <th>Derived class</th>
  	<td>Field is not accessible.</td>
  	<td>Field is not accessible.</td>
  	<td>Field is not accessible.</td>
  	<td>Class is not visible.</td>
  </tr>
  <tr>
    <th>Unrelated class</th>
  	<td>Field is not accessible.</td>
  	<td>Field is not accessible.</td>
  	<td>Field is not accessible.</td>
  	<td>Class is not visible.</td>
  </tr>
</table>
