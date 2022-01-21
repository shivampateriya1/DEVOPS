## What are Elastic IP addresses?
  An Elastic IP address is a static IPv4 address designed for dynamic cloud computing. An Elastic IP address is allocated to your AWS account, and is yours until you release it. By using an Elastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account. Alternatively, you can specify the Elastic IP address in a DNS record for your domain, so that your domain points to your instance. For more information, see the documentation for your domain registrar, or Set up dynamic DNS on Your Amazon Linux instance.

An Elastic IP address is a public IPv4 address, which is reachable from the internet. If your instance does not have a public IPv4 address, you can associate an Elastic IP address with your instance to enable communication with the internet. For example, this allows you to connect to your instance from your local computer.

## S3 commands
  cp  copy
  syntax 
   cp  <LocalPath> <S3Uri> or <S3Uri> <LocalPath> or <S3Uri> <S3Uri>
  
  ls  list
  ls <S3Uri> or NONE
   
  mb
  aws s3 mb s3://mybucket
  
  mv Move command
    mv <LocalPath> <S3Uri> or <S3Uri> <LocalPath> or <S3Uri> <S3Uri>
  
  rm
  The following rm command deletes a single s3 object:
  aws s3 rm s3://mybucket/test2.txt

## What does SCP use?
  The SCP is a network protocol, based on the BSD RCP protocol, which supports file transfers between hosts on a network. SCP uses Secure Shell (SSH) for data         transfer and uses the same mechanisms for authentication, thereby ensuring the authenticity and confidentiality of the data in transit.
