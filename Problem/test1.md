### How to do we connect VPC from two different regions in AWS cloud
```terraform
region 1 : North Viginia 
region 2 : North Califonia


Testing : 
   Ec2 --> telnet port 22 [region - North Viginia] --> IP [Region - North Califonia]
   
 North Vigina Setup : 
 
 Step 1 : 
   Create VPC [NV-VPC] : 10.0.0.0/16
   subnet : public --> 10.0.0.1/24
   
 Step 2 : 
   Create Internet Gateway and attach to VPC [NV-VPC]
   
 Step 3 :
    Change the Route table for NV-VPC
       Add route 0.0.0.0/0 to IG
 
 Step 4 : 
     Create SG 
     Add inbound port 22 
     
 Transient Gateway : 
 
 Step 1 : 
    Create TG [NV-TG]
        TAG: NV-TG
        ASN: 40000000
        CIDR : Optional 
 Step 2: Add VPC as an attachment 
    Transient Gateway attachments [NV-TG-VPC]
        Transient Gateways ID 
        Attachment type : VPC 
        Subnet ID 
        Tags: Optional
 Step 3:
       Verify in the transient gateway route table --> propogations
 Step 4: 
       Update the Security Group for adding port 23 [cidr of NC block]
 Step 5: 
       Modify the vpc to route the traffic of the VPC to the Transient Gateway
 ```
       
    
    
    
    
    
    
    
    
    
    
    
    
    
    
 
         
