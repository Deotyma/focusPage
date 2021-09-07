<script>
	import NavBar from "./Components/NavBar.svelte";
	import Home from "./Vues/Home.svelte";
	import MOC from "./Vues/MOC.svelte";
	import Recherches from "./Vues/Recherches.svelte";
	import Blog from "./Vues/Blog.svelte";
	import {Router, Route, Link} from "svelte-routing";
</script>

<Router>
	<NavBar />
	<Route path="/" component={Home}/>
	<Route path="/home" component={Home}/>
	<Route path="/moc" component={MOC}/>
	<Route path="/recherches" component={Recherches}/>
	<Route path="/blog" component={Blog}/>
</Router>

<style>
	
</style>