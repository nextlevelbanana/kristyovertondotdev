<script>
	import FlyOut from "./FlyOut.svelte";
	import Bubble from "./Bubble.svelte";
	
	let name = 'world';
	
	let linguistics = [
		"This doesn't mean I judge your grammar!",
		"This DOES mean I have a whole rant about why naming things is specifically hard in English."
	]
	let js = [
		"Node, React, Svelte, VanillaJS, Angular.",
		"I have yet to use Vue but keep casting longing looks in its direction."
	]
	let ux = [
		"I have another whole rant about how UX should ALWAYS be your priority.",
		"Code needs good UX. Docs need good UX. Meetings need good UX!...",
		"Everything is UX."
	]
	let ui = [
		"Backend work is interesting in its own way,",
		"but generating something that looks cool is way more satisfying."
	]
	let db = [
		"Relational databases are great!",
		"And document databases have their uses!",
		"But the mental model of the graph is just easier to work with."
	]
</script>

<style>
	a, a:hover {
		color: #0066A4;
	}
	ul {
		list-style-type: none;
		padding: 0;
	}
	section {
		margin-bottom: 3rem;
	}
	.content {
		display: flex;
		flex-direction: column;
	}
</style>

<h1>Hello world. I'm Kristy.</h1>
<div class="content">
<section>
<p> I'm a software engineer with a background in 
<FlyOut name="linguistics">
		<Bubble bubbles={linguistics}>
		</Bubble>
</FlyOut>.
</p>

<p> I love 
<FlyOut name="JavaScript">
	<Bubble bubbles={js}>
		</Bubble>
</FlyOut>, 
<FlyOut name="UX">
	<Bubble bubbles={ux}>
		</Bubble>
</FlyOut>,
	<FlyOut name="UI">
		<Bubble bubbles={ui}>
		</Bubble>
	</FlyOut>, and
	<FlyOut name="graph databases">
		<Bubble bubbles={db}>
		</Bubble>
	</FlyOut>.
</p>
</section>
<section>
<p>
	I live in Portland, Oregon, where I help organize <a href="https://donutjs.club" target="_blank">DonutJS</a>.
</p>

<p>
	In my free time, I like to <a href="https://nextlevelbanana.itch.io" target="_blank">make games</a>.
</p>
</section>
<section>
<ul>
	<li><a href="https://github.com/nextlevelbanana/" target="_blank">GitHub, aka museum of abandoned weekend projects</a></li>
	<li><a href="https://www.linkedin.com/in/kristyoverton/" target="_blank">LinkedIn</a></li>
	<li><a href="mailto:kristy@overton.club">email: kristy at overton dot club</a></li>
</ul>
</section>
<footer>
	<p>Built with Svelte, deployed ... tbd</p>
</footer>
</div>