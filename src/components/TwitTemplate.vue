<script>
    export default{
        props: [
            'text', 
            'author'
        ]
    }
</script>

<template>
    <article class="twit">
        <div class="twit-icon">
            <i class="fas fa-bullhorn"></i>
        </div>
        <div class="twit-content">
            <p class="twit-text">
                {{ text }} 
            </p>
            <p class="twit-author">
                <a href="#">{{ author }}</a>
            </p>
        </div>
    </article>
</template>

<style>
.twit {
    flex: 0 1 28%;
    display: flex;
    margin: 2px;
    padding: 20px;
    border: 1px solid #dadada;
    border-radius: 2px;
    background-color: #fff;
}

.twit-icon {
    font-size: 24px;
}

.twit-content {
    flex: 1 1 80%;
    margin-left: 10px;
}

.twit-content p {
    margin: 0;
}

.twit-content .twit-author {
    margin-top: 8px;
    text-align: right;
    font-weight: bold;
}
</style>