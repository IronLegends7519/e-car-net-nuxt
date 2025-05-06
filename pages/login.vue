<script>
import profil from './profil/index.vue';

export default {
    setup() {
        const email = ref('')
        const password = ref('')

        const login = (event) => {
            event.preventDefault() 
                   for(let i = 0; i < utilisateur.length; i++){
                        console.log(utilisateur[i].email)
                        console.log(utilisateur[i].password)
                        console.log(email.value)
                        console.log(password.value)
                       if(utilisateur[i].email === email.value && utilisateur[i].password === password.value){
                        //    navigateTo(profil.vue)
                           alert('connexion reussi')
                           return
                       }
                       else{
                           alert('email ou mot de passe incorrect')
                       }
                   }
    }
}
}


</script>

<template>
    <div>
        <h1>Connexion</h1>
        <form @submit="login">
        <input type="text" v-model="email" placeholder="email" />
        <input type="password" v-model="password" placeholder="password" />
        <button type="submit">Connexion</button>
        </form>
    </div>
</template>

