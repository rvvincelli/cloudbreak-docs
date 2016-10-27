# Custom Cloud Images
Every cloud platform comes with default images that contain packages required to build an Ambari and HDP stack. These default images are declared in yml files, which Cloudbreak loads upon start. You can customize these images and use them instead of the defaults. 

To overwrite the default yml files, place files declaring your custom images in the `/var/lib/cloudbreak-deployment/etc` directory. The etc directory does not exist by default so you need to create it.

The format of the yml files is platform-specific and described in the following sections.  

>`Note:` If you wish to change the images after Cloudbreak has been launched, you need to restart the application after updating the images.
 
## AWS
To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/aws-images.yml` and replace its content by region as desired. The default content of the yml file is:
```
aws:
  ap-northeast-1: ami-49ce6928
  ap-northeast-2: ami-bbf521d5
  ap-southeast-1: ami-959731f6
  ap-southeast-2: ami-8d86b4ee
  eu-central-1: ami-bcfd04d3
  eu-west-1: ami-4b206f38
  sa-east-1: ami-2971ec45
  us-east-1: ami-8a0d5c9d
  us-west-1: ami-62cc8402
  us-west-2: ami-97bd18f7
```

## Azure
To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/arm-images.yml` and replace its content by region as desired. The default content of the yml file is:
```
azure_rm:
  East Asia: https://sequenceiqeastasia2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  East US: https://sequenceiqeastus12.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Central US: https://sequenceiqcentralus2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  North Europe: https://sequenceiqnortheurope2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  South Central US: https://sequenceiqouthcentralus2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  North Central US: https://sequenceiqorthcentralus2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  East US 2: https://sequenceiqeastus22.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Japan East: https://sequenceiqjapaneast2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Japan West: https://sequenceiqjapanwest2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Southeast Asia: https://sequenceiqsoutheastasia2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  West US: https://sequenceiqwestus2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  West Europe: https://sequenceiqwesteurope2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Brazil South: https://sequenceiqbrazilsouth2.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Canada East: https://sequenceiqcanadaeast.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
  Canada Central: https://sequenceiqcanadacentral.blob.core.windows.net/images/cb-2016-10-18-08-46.vhd
```

## GCP
To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/gcp-images.yml` and replace its content as desired. It is not required to have an image in every region, as the `default` is used everywhere. The default content of the yml file is:
```
gcp:
  default: sequenceiqimage/cb-2016-10-18-08-46.tar.gz
```

## OpenStack
To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/os-images.yml` and replace its content as desired. It is not required to have an image in every region, as the `default` is used everywhere. The default content of the yml file is:
```
openstack:
  default: cloudbreak-2016-10-18-08-46
```