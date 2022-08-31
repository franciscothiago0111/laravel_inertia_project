<script>

    
    import { useToast} from "vue-toastification";
    
    export default({
        setup() {
          // Get toast interface
          const toast = useToast();
         
          return { toast }
        },
    
        props:{
            
            type: {
                type: String,
                default: ''
            },
            message: {
                type: String,
                default: ''
            }
        },
    
        watch: {
            message:{
                handler: 'someActions',
                immediate: true,
                deep: true,
            },
            type:{
                immediate: true,
                deep: true,
            },
      },
    
        methods:{
            someActions(){
                if(this.message){
                   let tipo = this.type
                    this.toast(this.message, {
                    type: tipo // or "success", "error", "default", "info" and "warning"
                    });
                }
               
            }
        }
        
    })    
    
    </script>
    
    