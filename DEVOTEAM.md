# COMMAND
  gcloud components update
  gcloud auth application-default login
  gradlew clean googleJavaFormat build publish -x test

⚠️ Attention : si une version sur le repo maven du projet youmaps-api existe deja (ex 2.0.0) -> erreur 400, ca n'écrase pas
  Could not PUT 'https://europe-west2-maven.pkg.dev/youmaps-api/maven-devoteam/devoteam-youmaps/google-maps-services/2.0.0/google-maps-services-2.0.0.jar'. Received status code 400 from server: Bad Request

  On construit un "fat-jar" avec id 'com.github.johnrengelman.shadow' version '8.1.1'
  Ca contient les classes com.google.maps qui serviront ailleurs.

  Modificiation suite ua fork : 

  ## PendingResultBase

  -> Suppression du "final" :  private GeoApiContext context;
  -> Ajout :
  
    public void setContext(GeoApiContext context) {
      this.context = context;
    }
    
    public HashMap<String, List<String>> getParams() {
      return params;
    }

    public void setParams(HashMap<String, List<String>> params) {
      this.params = params;
    }
