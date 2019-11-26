<template>
    <div>
        <header class="header dark">
            <v-container class="py-5">
                <v-layout align-center row>
                    <router-link to="/" class="logo" style="cursor: pointer">
                        <img src="/images/nj-white.png" width="120" title="NJ" />
                    </router-link>
                    <div class="layout justify-end">
                        <nav>
                            <ul class="link-list">
                                <li>
                                    
                                    <nuxt-link :to="{ path: '/', hash:'#servicos'}" v-scroll-to="'#servicos'" >
                                        Serviços
                                    </nuxt-link>
                                </li>
                                <li>
                                    <nuxt-link :to="{ path: '/',hash:'#comoFunciona'}" v-scroll-to="'#comoFunciona'" >
                                        Como funciona   
                                    </nuxt-link>
                                    
                                </li>
                                <li>
                                    <nuxt-link :to="{ path: '/',hash:'#action'}" v-scroll-to="'#action'">
                                        Fale com a Job
                                    </nuxt-link>
                                </li>
                            
                            </ul>
                        </nav>
                    </div>
                </v-layout>
            </v-container>
            
        </header>
    </div>
</template>