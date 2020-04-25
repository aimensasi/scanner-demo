<template>
  <div>
    <StreamBarcodeReader
    v-if="scan"
    @decode="onDecode"
    @loaded="onLoaded"
    ></StreamBarcodeReader>
    <button class="btn btn-primary" @click="() => scan = true" v-if="!scan">Scan</button>
  </div>
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";

export default {
    components: {
        StreamBarcodeReader,
    },
    data: function(){
        return { 
            scan: false,
        };
    },
    mounted(){
        console.log("Mounted...");
    },
    methods: {
        onDecode: function(result){
            console.log(result);
            this.scan = false;
        },
            onLoaded: function(result){
            console.log(result)
        }
    }
}
</script>
