<template>
    <div class="hello">

        <el-input placeholder="Please input" v-model="keyword">
            <template slot="prepend">Search Product: </template>
        </el-input>

        <div class="pt-1">
            <el-row>
                <el-button @click="searchOn(site)" v-for="site in sites.malaysia" v-bind:key="site.name" round>{{site.name}}</el-button>
            </el-row>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        },
        data(){
            return {
                keyword: "",
                sites: {
                    "malaysia": [
                    {
                        "name": "Lazada",
                        "url": "https://www.lazada.com.my/catalog/?q={query}",
                        "type": "all"
                    },
                    {
                        "name": "Shopee",
                        "url": "https://shopee.com.my/search?keyword={query}",
                        "type": "all"
                    },
                    {
                        "name": "Lelong",
                        "url": "https://www.lelong.com.my/catalog/all/list?TheKeyword={query}",
                        "type": "p2p"
                    },
                    {
                        "name": "Zalora",
                        "url": "https://www.zalora.com.my/catalog/?q={query}",
                        "type": "fashion"
                    },
                    {
                        "name": "GoShop",
                        "url": "https://www.goshop.com.my/search?keyword={query}",
                        "type": "tv-marketing"
                    },
                    {
                        "name": "eBay (MY)",
                        "url": "https://www.ebay.com.my/sch/i.html?_nkw={query}",
                        "type": "all"
                    },
                    {
                        "name": "Hermo",
                        "url": "https://www.hermo.my/search/product?keyword={query}",
                        "type": "fashion"
                    },
                    {
                        "name": "Qoo10",
                        "url": "https://www.qoo10.my/s/?keyword={query}",
                        "type": "all"
                    },
                    {
                        "name": "PrestoMall",
                        "url": "https://www.prestomall.com/totalsearch/TotalSearchAction/searchTotal.do?kwd={query}",
                        "type": "all"
                    },
                    {
                        "name": "Fashion Valet",
                        "url": "https://www.fashionvalet.com/catalogsearch/result/?q={query}",
                        "type": "fashion"
                    },
                    {
                        "name": "Mudah",
                        "url": "https://www.mudah.my/Malaysia/{query}-for-sale?q={query}",
                        "type": "p2p"
                    },
                    {
                        "name": "EZBuy",
                        "url": "https://ezbuy.my/category/?keyWords={query}",
                        "type": "all"
                    },

                    ]
                }
            }
        },
        methods: {
            searchOn(site) {
                window.open(site.url.replace("{query}", this.keyword), "_blank");
                focus();
            }
        } 
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
