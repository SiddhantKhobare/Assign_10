pipeline
{  
   environment
   {
     registry = "siddhantkhobare/demoimage"
     resgistryCredential = 'dockerid'
     dockerImage = ''
   }
 agent any
 
 stages
 
 {
    stage ('Biuld image')
    {
       steps
       { 
         script
         {    
             dockerImage= docker.build registry  :"$BUILD_NUMBER"
         }
      }
   }
   
   stage (Deploy the image)
   { 
        steps
       { 
         script
         {    
            docker.withRegistry ('', registryCredential)
            {
                dockerImage.push()
            }
          }
       }   
    }
   
   
   
