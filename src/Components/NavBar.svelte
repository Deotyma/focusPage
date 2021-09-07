<script>
import { Link } from "svelte-routing"

    let src = "assets/focus3.png"
    let toggelMenu = false

    function toggelMenuRes(){
        toggelMenu = !toggelMenu
    }
</script>

<nav>
    <div class="logo">
        <img {src} alt="logo focus">
    </div>

    <ul class={toggelMenu ? "list-nav visible" : "list-nav"}>
        <Link to="/" title="A propos">A Propos</Link>
        <Link to="/moc" title="MOC">MOC</Link>
        <Link to="/recherches"title="Recherches">Science</Link>
        <Link to="/blog" title="Blog">Blog</Link>
    </ul>

    <div on:click={toggelMenuRes} class="hamburger">
        <div>&#9776</div>
    </div>

</nav>

<style>
    nav{
        height: 70px;
        width: 100vw;
        background-color:#0000AA;
        position: relative;
    }
    .logo{
        position: absolute;
        top: 5px;
        left: 10px;
    }
    .logo img{
        height: 60px;
    }

    .list-nav{
        list-style-type: none;
        display: flex;
        justify-content: center;
        height: 100%;
        align-items: center;
    }
    .hamburger{
       position: absolute;
       top: 5px;
       right: 10px;
       font-size: 2.5rem;
       color: white;
       display: none;
       }
    @media only screen and (max-width:650px){
        .hamburger{
            display: block;
            cursor: pointer;
        }
        ul{
            padding: 0;
        }
        .list-nav{
            flex-direction: column;
            position: relative;
            top: 70px;
            display: none;
        }
        .list-nav.visible{
            display: flex;
            flex-direction: column;
        }
    }
</style>

