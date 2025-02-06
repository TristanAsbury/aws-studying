> [!Definition]
> A hosted zone is a **container for records**, and records contain information about how you want to route traffic for a specific domain, such as `example.com`, and its subdomains (`acme.example.com`, `zenith.example.com`). A hosted zone and the corresponding domain have the same name. There are two types of hosted zones:

### Public
- _Public hosted zones_ contain records that specify how you want to route traffic on the internet. For more information, see [Working with public hosted zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/AboutHZWorkingWith.html).

### Private
- _Private hosted zones_ contain records that specify how you want to route traffic in an Amazon VPC. For more information, see [Working with private hosted zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html).