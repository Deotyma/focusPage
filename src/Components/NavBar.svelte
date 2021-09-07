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
        <div class="item-nav"><Link to="/" title="A propos">A Propos</Link></div>
        <Link to="/moc" class="item-nav" title="MOC">MOC</Link>
        <Link to="/recherches" class="item-nav" title="Recherches">Science</Link>
        <Link to="/blog" class="item-nav" title="Blog">Blog</Link>
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
    .list-nav li a{
        color: white;
        text-decoration: none;
        margin: 0 10px;
        font-weight: bold;
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
                display: block;
            }
            .item-nav{
                width: 100vw;
                background-color: #0000AA;
                text-align: center;
                padding: 0 10px;
                margin: 0;
            }
        }
</style>

