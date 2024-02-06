# Terraform-AWS-Budget-Test
This is a little project I undertook in order to introduce myself to terraform  and AWS


# Specify the required providers and their versions
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

# Configure the AWS provider with the desired region
provider "aws" {
  region = "us-east-1"
}

# Define an AWS Budget resource
resource "aws_budgets_budget" "Test-Case" {
  name              = "monthly-budget"
  budget_type       = "COST"
  limit_amount      = "20.00"
  limit_unit        = "USD"
  time_unit         = "MONTHLY"
  time_period_start = "2024-02-05_00:01"
}
