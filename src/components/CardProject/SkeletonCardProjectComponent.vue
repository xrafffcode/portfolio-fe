<template>
    <div class="card">
        <div class="box-skeleton-image"></div>
        <div class="card-body">
            <div class="box-skeleton"></div>
            <br>
            <div class="box-skeleton"></div>
            <br>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>
</template>
<script>
export default {

}
</script>
<style>
.box-skeleton {
    width: 100%;
    height: 20px;
    background-color: #f7f7f7;
    background-image: linear-gradient(90deg, #f7f7f7 0px, #e8e8e8 40px, #f7f7f7 80px);
    background-size: 200px 100%;
    animation: shimmer-animation 1s infinite linear;
    border-radius: 4px;
    overflow: hidden;
}

.box-skeleton-image {
    width: 100%;
    height: 200px;
    background-color: #f7f7f7;
    background-image: linear-gradient(90deg, #f7f7f7 0px, #e8e8e8 40px, #f7f7f7 80px);
    background-size: 200px 100%;
    animation: shimmer-animation 1s infinite linear;
    border-radius: 4px;
    overflow: hidden;
}

@keyframes shimmer-animation {
    0% {
        background-position: -200px 0;
    }

    100% {
        background-position: 200px 0;
    }
}
</style>