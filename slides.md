% Programmer's Learning Machine
% Matthieu Nicolas
% IJD seminar - March 03, 2015

# What is PLM

> - Software to learn programming
> - Allows students to progress at their own speed...
> - ... while the teacher helps the ones having trouble
> - Used at *TELECOM Nancy* since 2008 

# Current state

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
- More user-friendly
- Gamification

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

## User tracking { data-transition="none" }

- **git** as a database management system

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

------

## User tracking { data-transition="none" }

- Data pushed anonymously to a **GitHub** repository...
- ... but lost some tracks
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

## Server-side { data-transition="none" }

- Refactoring **PLM** into a library
- Set up a server using **Play framework**

<img data-src="img/play.svg" alt="Play Framework" width="30%" height="30%"/>

------

## Client-side { data-transition="none" }

- Built with **AngularJS** and **Foundation**
- Dialog with the server using **Websockets**

<img data-src="img/foundation-angular.png" alt="Foundation + AngularJS" width="20%" height="20%"/>

------

## Client-side { data-transition="none" }

- **TODO:** Video instead?

<img data-src="img/webPLM.png" alt="webPLM" width="80%" height="80%"/>


# Results

- Main functionalities implemented
- First universe adapted
- Only as a local server

# Next steps

- Set up the **CI** for **webPLM**
- Convert other universes
- Add debug mode
- Add **C** language

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
