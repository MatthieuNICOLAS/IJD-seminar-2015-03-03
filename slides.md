% Programmer's Learning Machine
% Matthieu Nicolas
% IJD seminar - March 03, 2015

# What is PLM

> - Software to learn programming
> - Allows students to progress at their own speed...
> - ... while the teacher helps the ones having trouble
> - Used at *TELECOM Nancy* since 2008 

# State before ADT

------

## Overview { data-transition="none" }

<img data-src="img/screen-PLM-1.png" alt="PLM" width="60%" height="60%"/>

------

## Overview { data-transition="none" }

<img data-src="img/screen-PLM-2.png" alt="PLM" width="60%" height="60%"/>

------

## Overview { data-transition="none" }

<img data-src="img/screen-PLM-3.png" alt="PLM" width="60%" height="60%"/>

------

## 200 exercises { data-transition="none" }

<img data-src="img/welcome.png" alt="Welcome" width="80%" height="80%"/>

------

## 200 exercises { data-transition="none" }

<img data-src="img/hanoi.png" alt="Hanoï" width="80%" height="80%"/>

------

## 200 exercises { data-transition="none" }

<img data-src="img/lunar-landing.png" alt="Lunar landing" width="80%" height="80%"/>

------

## Programming languages

<img data-src="img/programming-languages-logos.svg" alt="Programming Languages"/>

------

## Languages

<img data-src="img/languages-flags.svg" alt="Flags"/>

------

## User tracking { data-transition="none" }

- Keep the students' sessions
- Track the students' progress

------

## User tracking { data-transition="none" }

- **git** used in order to version the student's code
- Local repository and anonymous branch
- Data pushed to a **GitHub** repository

<img data-src="img/git.png" alt="Git" width="50%" height="50%"/>

------

## User tracking { data-transition="none" }

- User's actions stored as commits

<pre><code data-trim>{ 
	kind:"executed",
	lang:"Java",
	exo:"welcome.lessons.welcome.instructions.Instructions", 
	passedtests:"1",
	totaltests:"1",
	outcome:"pass"
}</code></pre>

# ADT's goals

------

## Improve the software's quality

<div class="notes">
	- Fix known bugs
	- Set up Continuous Integration
	- More features
</div>

------

## Attract students

- More teaching content
- Webification
- Gamification

<div class="notes">
	- Webification => MOOC, pouvoir monter un MOOC de programmation à partir des exos de PLM
	- Renforcer l'attention des élèves
		- 1% de rétention dans les MOOCs
</div>

------

## And teachers

- Keep track of the students' progress
- Adapt content to their needs
- Able to add their own exercises

------

## And researchers

- To an experimental teaching platform
- How to detect students having difficulties?
- What are the most common errors?

# Work done

------

## First steps

- Back-to-school season
	- Got the students' feedback...
	- ... and 170 bug reports
- Solved minor issues

------

## Debug user tracking

- Lost data
- Fixed and refactored the code

------

## Unit testing

- Need to ensure the critical parts
	- **git**
	- exercises' solutions
	- lessons

------

## Continuous Integration { data-transition="none" }

<div class="notes">
- Execute tests automatically
	- when push to *master*
	- or a pull-request is created
</div>

<img data-src="img/travis-ci.svg" alt="Travis CI" width="50%" height="50%"/>

------

## Continuous Integration { data-transition="none" }

- Execute tests automatically when
	- someone push to *master*
	- a pull-request is created
- Notify us when the build state change
<!--
<div class="notes">
- Easily configurable:
</div>

<pre><code data-trim>language: scala
scala:
  - 2.10.5
jdk:
  - openjdk7
env:
  - TEST_SUITE=unit-tests
  - TEST_SUITE=integration-tests
script:
  - ant $TEST_SUITE
notifications:
  recipients:
    - martin.quinson@loria.fr
    - gerald.oster@loria.fr
    - matthieu.nicolas@loria.fr
  email:
    on_success: change
    on_failure: always
  template:
    - "%{repository}/%{branch} (%{commit} - %{author}): %{message}"</code></pre>
-->

------

## To a web app

------

## Play Framework { data-transition="none" }

- Java and Scala web application framework
- Allow to set up application server

<img data-src="img/play.svg" alt="Play Framework" width="30%" height="30%"/>

------

## MVC pattern { data-transition="none" }

<img data-src="img/architecture-diagram-1.png" alt="PLM" width="60%" height="60%"/>

------

## Actors { data-transition="none" }

- Concurrent and scalable
- *'Let it crash'*

<img data-src="img/architecture-diagram-2.png" alt="PLM" width="50%" height="50%"/>

------

## Working with websockets { data-transition="none" }

- Controller only needed to render views
- One actor per websocket

<img data-src="img/architecture-diagram-3.png" alt="PLM" width="50%" height="50%"/>

------

## Refactor PLM { data-transition="none" }

- To be used as a library
- Remove the current UI
- Keep track of the world's evolution

------

## Refactor PLM { data-transition="none" }

- Has to update the server's and the client's world model
- Each time the world is modified...
<pre><code data-trim>setBugglePosition(newX, newY)</code></pre>
- ... the corresponding operation is generated
<pre><code data-trim>//Operation stored then send to the client
moveBuggleOperation(oldX, oldY, newX, newY)</code></pre>

------

## Client-side { data-transition="none" }

- One-page application built with **AngularJS**
- UI made with **Foundation**

<img data-src="img/foundation-angular.png" alt="Foundation + AngularJS" width="20%" height="20%"/>

------

## Client-side { data-transition="none" }

<video controls>
	<source data-src="video/webPLM.mp4" type="video/mp4">
</video>

# Results

- Main functionalities implemented
- First universe adapted
- Only as a local server

# Next steps

- Convert other universes
- Embed debugging tools
- Support **C** language
- To a web server

------

## Thanks for listening

Do you have any questions?

<script>
	document.getElementsByAttribute = Element.prototype.getElementsByAttribute = function(attr) {
	    var nodeList = this.getElementsByTagName('*');
	    var nodeArray = [];

	    for (var i = 0, elem; elem = nodeList[i]; i++) {
	        if ( elem.getAttribute(attr) ) nodeArray.push(elem);
	    }

	    return nodeArray;
	};

	function reportAttributeToParent(attribute) {
		document.getElementsByAttribute(attribute).map(function (item) {
			var elt = document.getElementById(item.id);
			elt.parentNode.setAttribute(attribute, item.getAttribute(attribute));
			item.removeAttribute(attribute);
		});
	}

	reportAttributeToParent('data-transition');
</script>
