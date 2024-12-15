Analysis of Cricket Match using Spark in Google Cloud Platform(GCP)


### Steps to Run the Project

1. **Create a Cluster on GCP**  
   - Log in to the [Google Cloud Console](https://console.cloud.google.com/).  
   - Go to the **Dataproc** section and create a cluster.  
   - Choose the cluster name, region, and machine type as per the project requirements.  

2. **Upload Files to a GCP Bucket**  
   - Navigate to **Cloud Storage** and create a new bucket or use an existing one.  
   - Upload the necessary files (e.g., datasets, scripts) to this bucket using the UI or `gsutil` command-line tool:  
     ```bash
     gsutil cp <local_file_path> gs://<bucket_name>/
     ```  

3. **Start a Spark Session**  
   - SSH into the Dataproc cluster's master node via the GCP Console or `gcloud` CLI:  
     ```bash
     gcloud compute ssh <cluster-name>-m --region=<region>
     ```  
   - Start a Spark session from within the cluster:  
     ```python
     from pyspark.sql import SparkSession
     spark = SparkSession.builder.appName("MyProject").getOrCreate()
     ```  

4. **Open Jupyter Notebook**  
   - Enable the Jupyter Notebook service for your Dataproc cluster:  
     ```bash
     gcloud dataproc clusters update <cluster-name> --region=<region> --enable-component-gateway
     ```  
   - Access the Jupyter Notebook using the link provided in the GCP Console’s **Component Gateway** section.  
   - Open your notebook to execute the project.  


