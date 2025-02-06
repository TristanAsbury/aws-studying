#Infrastructure 
## Public "Internet" Zone
- "The Internet"
## "AWS Public" Zone
- Where public facing services such as S3 are
- When connecting to this zone, the connection goes through the public internet first
- Anyone can connect, but permissions are required to access the service
## "AWS Private" Zone
- Usually secured and require some type of authentication
- Accessible from other VPC or on-premises networks as long as private networking is configured