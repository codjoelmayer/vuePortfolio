<template>
    <nav id="header" :class="{headerBgColor: applyStyle}" class="navbar navbar-expand-lg bg-dark navbar-dark container-fluid position-sticky top-0">
        <div class="container">
            <ul class="navbar-nav me-auto">
                <li class="nav-item">
                    <router-link to="/" class="routerLink">
                        <img id="logo" class="img-fluid" src="https://i.postimg.cc/sxQ9v1g3/logo.jpg"  alt="logo"/>
                    </router-link> 
                </li>
            </ul>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon "></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0 py-4"> 
                    <li class="nav-item">
                        <router-link to="/" class="routerLink">About
                            <i class="bi bi-file-earmark-person"></i>
                        </router-link> 
                    </li>
                    <li class="nav-item">
                        <router-link to="/resume" class="routerLink">Resume
                            <i class="bi bi-file-person-fill"></i>
                        </router-link> 
                    </li>
                    <li class="nav-item">
                        <router-link to="/projects" class="routerLink">Project
                            <i class="bi bi-server"></i>
                        </router-link> 
                    </li>
                    <li class="nav-item">
                        <router-link to="/contact" class="routerLink">Contact
                            <i class="bi bi-person-lines-fill"></i>
                        </router-link> 
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            isScrolled: false,
            applyStyle: false,
            displayScrollY: '',
        }
    },
    methods: {
        handleScroll() {
            this.isScrolled = (window.scrollY > 10);
            if(this.isScrolled) {
                this.applyStyle = true;
            }else {
                this.applyStyle = false;
            }
        }
    },
    updated() {
        this.displayScrollY = window.scrollY;
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    }
}
</script>
<style scoped>
    #logo {
        width: 3em;
        object-fit: cover;
    }
</style>