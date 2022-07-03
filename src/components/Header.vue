<template>
     <nav class="navbar navbar-dark navbar-expand-md bg-dark py-3">
        <div class="container"><a class="navbar-brand d-flex align-items-center" href="#"><img class="logo" src="../assets/logo.png" alt=""><span>PokéVue</span></a>
            <!-- <div class="collapse navbar-collapse" id="navcol-5">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link active" href="#">First Item</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Second Item</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Third Item</a></li>
                </ul><a class="btn btn-primary ms-md-2" role="button" href="#">Button</a>
            </div> -->
        </div>
    </nav>
</template>

<script>
export default {
    name: 'Header_vue',
}
</script>

<style>
.logo{
    width: 50px;
    height: 50px;
}
</style>