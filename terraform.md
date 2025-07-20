

🌍 What is Terraform?

Terraform is an open-source Infrastructure as Code (IaC) tool developed by HashiCorp. It lets you define, provision, and manage infrastructure (servers, networks, databases, etc.) using declarative configuration files.

✅ Write code → 🛠 Plan changes → 🚀 Apply → ☁️ Infrastructure is created or updated.

⸻

🧱 Key Concepts & Components

⸻

1. Providers
	•	Plugins that allow Terraform to manage resources on platforms like AWS, Azure, GCP, Kubernetes, etc.
	•	Examples: aws, google, azurerm

provider "aws" {
  region = "us-east-1"
}


⸻

2. Resources
	•	The building blocks of your infrastructure — e.g., EC2 instances, S3 buckets, DBs.

resource "aws_instance" "web" {
  ami           = "ami-0abcdef1234567890"
  instance_type = "t2.micro"
}


⸻

3. Variables
	•	Input values that make configs reusable and dynamic.

variable "instance_type" {
  default = "t2.micro"
}

Use it:

instance_type = var.instance_type


⸻

4. Outputs
	•	Return values from your Terraform code, like IPs or URLs.

output "instance_ip" {
  value = aws_instance.web.public_ip
}


⸻

5. State
	•	Terraform keeps track of what resources it manages using a .tfstate file.
	•	It’s critical for tracking real vs desired infrastructure.

⸻

6. Modules
	•	A module is a container for multiple resources grouped together.
	•	Helps reuse and organize code.

module "vpc" {
  source = "./modules/vpc"
  cidr_block = "10.0.0.0/16"
}


⸻

⚙️ Terraform Workflow

terraform init     # Initialize the working directory
terraform plan     # Show what will be created/updated/destroyed
terraform apply    # Apply the changes to reach the desired state
terraform destroy  # Tear down the infrastructure


⸻

✅ Example: Launch an EC2 Instance on AWS

🔹 main.tf

provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "my_ec2" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  tags = {
    Name = "MyEC2Instance"
  }
}

output "instance_ip" {
  value = aws_instance.my_ec2.public_ip
}

💡 Run it:

terraform init
terraform apply


⸻

📌 Summary of Key Benefits:
	•	Declarative: Define “what” you want, not “how”.
	•	Idempotent: Running it multiple times won’t create duplicates.
	•	Multi-Cloud: One language, many platforms.
	•	Version Controlled: Infrastructure changes tracked like code.

⸻
