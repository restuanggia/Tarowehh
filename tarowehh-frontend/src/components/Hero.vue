<template>
    <div class="hero">
        <!-- dekstop -->
        <div class="d-none d-md-block">
            <div class="row mt-3">
                <div class="col-md-6">
                    <div class="d-flex h-100">
                        <div class="justify-content-center align-self-center">
                            <h2><strong>Tarowehh Chips Menu,</strong> <br>in Your Snacking</h2>
                            <p>Keripik Klasik yang Berbeda dengan Keunikan talas dalam bentuk keripik yang tiada duanya.</p>
                            <router-link class="btn btn-lg btn-success" to="/foods"><b-icon-arrow-right></b-icon-arrow-right> Pesan</router-link>
                        </div>
                    </div>
                </div>
                <div class="col-md-6">
                    <img src="../assets/images/Hero.png" width="100%" alt="">
                </div>
            </div>
        </div>

        <!-- mobile -->
        <div class="d-sm-block d-md-none">
            <div class="row mt-4">
                <div class="col-md-6 mb-3">
                    <img src="../assets/images/Hero.png" width="100%" alt="">
                </div>
                <div class="col-md-6">
                    <div class="d-flex h-100">
                        <div class="justify-content-center align-self-center">
                            <h2><strong>Tarowehh Chips Menu,</strong> <br>in Your Snacking</h2>
                            <p>Keripik Klasik yang Berbeda dengan Keunikan talas dalam bentuk keripik yang tiada duanya.</p>
                            <button class="btn btn-lg btn-success"><b-icon-arrow-right></b-icon-arrow-right> Pesan</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld'
}
</script>

<style>

</style>
