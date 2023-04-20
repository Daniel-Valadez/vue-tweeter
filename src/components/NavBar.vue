<script>

</script>

<template>
    <a href="#"
        ><h1 class="site-title">
            <i class="far fa-hand-lizard"></i> tweeter
        </h1></a
    >
    <nav class="navbar">
        <ul class="navlist">
            <li class="navitem navlink active"><a href="#">Home</a></li>
            <li class="navitem navlink"><a href="#">Trending</a></li>
            <li class="navitem navlink"><a href="#">People</a></li>
            <li class="navitem navbar-search">
                <input
                    type="text"
                    id="navbar-search-input"
                    placeholder="Search..."
                />
                <button type="button" id="navbar-search-button">
                    <i class="fas fa-search"></i>
                </button>
            </li>
        </ul>
    </nav>
</template>

<style>
.site-title {
    margin: 0;
    padding: 10px 20px;
    font-size: 30px;
    font-weight: 100;
    background-color: #319df6;
    color: #fff;
}

.navbar {
    background-color: #fff;
    font-size: 18px;
    line-height: 22px;
}

.navlist {
    margin: 0 0 0 20px;
    padding: 0;
}

.navitem {
    display: inline-block;
}

a {
    color: #343434;
    text-decoration: none;
}

a:hover,
a:focus {
    color: #319df6;
}

a:focus {
    outline: none;
}

.navlink a {
    padding: 8px 10px;
    display: inline-block;
}

.navlink.active {
    box-shadow: inset 0 -3px #319df6;
}

.navbar-search {
    float: right;
    margin-right: 20px;
    padding: 0;
    line-height: 38px;
}

#navbar-search-input {
    padding: 4px;
    font-size: 16px;
    background-color: #eee;
    border: 1px solid #dadada;
    border-radius: 2px;
}

#navbar-search-input:focus {
    outline: none;
    background-color: #fff;
}

#navbar-search-button {
    /*margin-left: -5px;*/ 
    font-size: 16px;
    background: none;
    border: none;
    color: #343434;
    cursor: pointer;
}

#navbar-search-button:hover {
    color: #319df6;
}

#navbar-search-button:focus {
    color: #319df6;
    outline: none;
}
</style>
