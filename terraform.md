

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

📘 What is Terraform State?

Terraform uses a file called terraform.tfstate to keep track of the infrastructure it manages.
This file stores information about:
	•	Resources you’ve created
	•	Their current configuration
	•	Metadata (like IDs, IPs, etc.)

✅ Think of it as Terraform’s memory of what exists in the real world.

⸻

🧠 Why State is Important
	1.	Mapping real resources to config: Terraform uses state to know which real-world resources it is managing.
	2.	Change detection: It compares your .tf files to the current state to compute a plan.
	3.	Dependency tracking: Terraform understands which resources depend on others.
	4.	Performance: Reduces API calls to providers by caching resource info.

⸻

📂 Default Behavior

By default, state is stored locally in a file:

terraform.tfstate

But in a team or production setting, remote state is used.

⸻

🌐 Remote State (Recommended)

Remote state allows multiple people or systems to share the same state safely.

Backends supported:
	•	AWS S3
	•	Azure Blob Storage
	•	Google Cloud Storage
	•	HashiCorp Terraform Cloud
	•	Consul, etcd

📦 Example: Store State in S3 (AWS)

terraform {
  backend "s3" {
    bucket = "my-terraform-state-bucket"
    key    = "prod/terraform.tfstate"
    region = "us-east-1"
  }
}

🔒 Combine with DynamoDB to lock state and prevent concurrent changes.

⸻

🔐 State Locking

When multiple users are working with the same state:
	•	Terraform locks the state (in backends like S3 + DynamoDB).
	•	Prevents race conditions or corrupted state.

⸻

🛠️ Useful State Commands

Command	Purpose
terraform show	View current state
terraform state list	List all tracked resources
terraform state show <address>	Show details of a resource
terraform state rm	Remove a resource from state (Terraform stops managing it)
terraform state mv	Move resources in state (rename or move modules)


⸻

⚠️ Common Gotchas
	•	Don’t edit terraform.tfstate manually — it’s JSON, but dangerous.
	•	Always use terraform apply or import to change what’s tracked.
	•	Version control your .tf files, but not the .tfstate (especially with secrets inside).

⸻

✅ Best Practices
	•	Use remote state for collaboration.
	•	Enable state locking.
	•	Use state encryption at rest and in transit.
	•	Keep state files secure — they may contain secrets (like passwords, access keys).

⸻

📌 Quick Summary

Feature	Local State	Remote State (e.g., S3)
Collaboration	❌ Not ideal	✅ Safe and shareable
Locking	❌ None	✅ With DynamoDB, etc.
Security	🔓 Risky	🔐 Use encryption


