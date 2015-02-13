% Programmer's Learning Machine
% Matthieu Nicolas
% March 03, 2015

# What is PLM

> - Software to learn programming
> - Allows students to progress at their own speed...
> - ... while the teacher helps the ones having trouble
> - Used at *TELECOM Nancy* since 2008 

# Existing

------

## Fat client

**TODO:** Talk about Java and Swing

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

## Improving the software

- Fix known bugs
- Set up Continuous Integration

------

## Attract students

- More teaching content
- More user-friendly
- Gamification

------

## And teachers

- Keep track of the students' progress
- Adapt content to their needs
- Able to add their own content

------

## And researchers

- To an experimental teaching platform
- How to detect students having difficulties?
- What are the most common errors?

# Work done

------

## First steps

------

## User tracking { data-transition="none" }

- **Git** as a database management system

<img data-src="img/git.png" alt="Git" width="50%" height="50%"/>

------

## User tracking { data-transition="none" }

- User's actions stored as commits

<pre><code data-trim>{ 
	kind:"executed", passedtests:"1", totaltests:"1", 
	course:"", exoInterest:"(please choose)", lang:"Java", 
	exo:"welcome.lessons.welcome.instructions.Instructions", 
	outcome:"pass"
}</code></pre>

------

## User tracking { data-transition="none" }

- Data pushed anonymously to a GitHub repository...
- ... but lost some tracks

------

## Unit testing & CI

------

## To a web app

# Results

# Next steps

- Convert other universes
- Add debug mode
- Add C language

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
