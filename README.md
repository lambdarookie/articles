# programming-articles

**A loose collection of articles I have written**

![Java Duke](https://32jn1p2jfust2jm6d92xtg5d-wpengine.netdna-ssl.com/wp-content/uploads/2017/07/duke_baker.png)

---

* **programming-articles** has been created by Lucas Baerenfaenger ([@lambdarookie](https://github.com/lambdarookie), [lambdarookie.com](https://lambdarookie.com)).
* It is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

+ 12 Jun 2018 - [Resources to Learn and Master JavaScript](#12-jun-2018---resources-to-learn-and-master-javascript)
+ 11 Feb 2018 - [The Ultimate Java Access Modifiers Table](#11-feb-2018---the-ultimate-java-access-modifiers-table)

---

## 12 Jun 2018 - Resources to Learn and Master JavaScript

Learning JavaScript is hard.
This is also due to the fact that it is very hard to identify good learning resources.
In the following, I share what I believe are some of the best resources to learn and master JavaScript.

One thing I assume, though, is that the reader is familiar with the general concepts of programming and computing.
There are many good books out there that teach those to complete novices.
Some of them even teach JavaScript as a first language, e.g., [Marijn Haverbeke](https://twitter.com/marijnjh)’s [Eloquent JavaScript](https://eloquentjavascript.net/) (free online version available).

It is essential to get to know the inner workings of JavaScript.
That is, because oftentimes it may _look_ similar to very common languages such as Java, C#, etc., but it really _is_ fundamentally different from those.
There is one book that I recommend to everyone who is starting out with JavaScript programming:
[The Principles Of Object-Oriented JavaScript](https://nostarch.com/oojs), written by [Nicholas C. Zakas](https://twitter.com/slicknet), published by [No Starch Press](https://nostarch.com/) – the self-proclaimed “finest in geek entertainment”.
Having read this book, one is equipped with a fundamental understanding of how JavaScript handles object-oriented programming (OOP), which allows one to avoid the most common misunderstandings and mistakes.
If you only have time to read one book before your project starts, this one should be it!
Another book that gives a great introduction into JavaScript’s so-called prototype-based style of OOP is [Kyle Simpson](https://twitter.com/getify)’s [You Don’t Know JS: this & Object Prototypes](https://github.com/getify/You-Dont-Know-JS/tree/master/this%20%26%20object%20prototypes) (free online version available).
This book also focuses on what the `this` keyword means in JavaScript, which is another great source of pain for many JavaScript developers.

At this point, it is obvious that the JavaScript source code to be found in the aforementioned books looks nothing like the source code to be found in modern JavaScript projects.
Nowadays, those projects use newer versions of JavaScript, e.g., ECMAScript 6 (ES6), which was finalized in 2015, ES7 from 2016, etc.
The aforementioned books teach valuable lessons on how JavaScript _works_ under the hood, however, it is also important to know what modern JavaScript _looks_ like.
[Venkat Subramaniam](https://twitter.com/venkat_s) introduces these concepts in his 2018-book [Rediscovering JavaScript: Master ES6, ES7, and ES8](https://pragprog.com/book/ves6/rediscovering-javascript).
His entertaining teaching style can also be witnessed in his talks, one of which, [Rediscovering JavaScript](https://www.youtube.com/watch?v=hUVBbL9C41M) (available for free on YouTube), accompanies the respective book.
A more detailed and highly praised introduction into ES6 is [Understanding ECMAScript 6](https://leanpub.com/understandinges6/read/) by Nicholas C. Zakas (free online version available).

Most people who learn JavaScript do so in order to work in front-end engineering.
At the time of this writing, one of the most popular “JavaScript librar[ies] for building user interfaces” is Facebook’s [React](https://reactjs.org/).
There is also Google’s [Angular](https://angular.io/), which I know almost nothing about, though.
People who want to build web apps or mobile apps using React, do yourselves a favor and check out the video courses by [Stephen Grider](https://twitter.com/ste_grider) on [Udemy](https://udemy.com/).
He takes one by the hand and shows one how to build industry-grade apps – comprehensibly and comprehensively.
I particularly enjoyed [Modern React with Redux](https://www.udemy.com/react-redux/) and [The Complete React Native and Redux Course](https://www.udemy.com/the-complete-react-native-and-redux-course/).

Finally, there is one programming topic that is very close to my heart, functional programming, which promises more elegant and less error-prone source code.
JavaScript is a very suitable candidate for this style of programming.
Hence, there are numerous books on how to apply this programing style to JavaScript.
[JavaScript Allongé](https://leanpub.com/javascriptallongesix/read) by [Reginald Braithwaite](https://twitter.com/raganwald) (free online version available) is a very high-quality book, which is, however, a very, very deep dive – so be warned.
A more casual introduction would be Kyle Simson’s [Functional Light JS](https://github.com/getify/Functional-Light-JS) (free online version available).

## 11 Feb 2018 - The Ultimate Java Access Modifiers Table

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
