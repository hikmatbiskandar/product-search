<template>
    <div class="hello">

        <el-input placeholder="Please input" v-model="keyword">
            <template slot="prepend">Search Product: </template>
        </el-input>

        <div class="pt-1">
            <el-row>
                <el-button :type="site.is_searching ? 'success' : ''" @click="toggleSelect(site)" v-for="site in sites.malaysia" v-bind:key="site.name" round>{{site.name}}</el-button>
                <el-button type="success"  @click="searchOnAll()" icon="el-icon-search" round>Go</el-button>
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
                        "type": "all",
                        "is_searching": true
                    },
                    {
                        "name": "Shopee",
                        "url": "https://shopee.com.my/search?keyword={query}",
                        "type": "all",
                        "is_searching": true
                    },
                    {
                        "name": "Lelong",
                        "url": "https://www.lelong.com.my/catalog/all/list?TheKeyword={query}",
                        "type": "p2p",
                        "is_searching": true
                    },
                    {
                        "name": "Zalora",
                        "url": "https://www.zalora.com.my/catalog/?q={query}",
                        "type": "fashion",
                        "is_searching": true
                    },
                    {
                        "name": "GoShop",
                        "url": "https://www.goshop.com.my/search?keyword={query}",
                        "type": "tv-marketing",
                        "is_searching": true
                    },
                    {
                        "name": "eBay (MY)",
                        "url": "https://www.ebay.com.my/sch/i.html?_nkw={query}",
                        "type": "all",
                        "is_searching": true
                    },
                    {
                        "name": "Hermo",
                        "url": "https://www.hermo.my/search/product?keyword={query}",
                        "type": "fashion",
                        "is_searching": true
                    },
                    {
                        "name": "Qoo10",
                        "url": "https://www.qoo10.my/s/?keyword={query}",
                        "type": "all",
                        "is_searching": true
                    },
                    {
                        "name": "PrestoMall",
                        "url": "https://www.prestomall.com/totalsearch/TotalSearchAction/searchTotal.do?kwd={query}",
                        "type": "all",
                        "is_searching": true
                    },
                    {
                        "name": "Fashion Valet",
                        "url": "https://www.fashionvalet.com/catalogsearch/result/?q={query}",
                        "type": "fashion",
                        "is_searching": true
                    },
                    {
                        "name": "Mudah",
                        "url": "https://www.mudah.my/Malaysia/{query}-for-sale?q={query}",
                        "type": "p2p",
                        "is_searching": true
                    },
                    {
                        "name": "EZBuy",
                        "url": "https://ezbuy.my/category/?keyWords={query}",
                        "type": "all",
                        "is_searching": true
                    },

                    ]
                }
            }
        },
        methods: {
            toggleSelect(site) {
                site.is_searching = !site.is_searching;
            },
            searchOnAll() {

                if (this.keyword == "") return false;

                for (var i = 0; i < this.sites.malaysia.length; i++) {
                    var single_site = this.sites.malaysia[i];
                    if (single_site.is_searching == true) window.open(single_site.url.replace(/{query}/g, this.keyword), "_blank");    
                }
                
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
