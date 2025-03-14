# Ansible User Management on GCP

## 📌 Project Overview
This project automates user management on Google Cloud Platform (GCP) instances using **Ansible**. It creates users, assigns them to groups, sets up SSH keys, and configures sudo privileges.

## 🚀 Features
- Create and manage users on GCP instances.
- Assign users to specific groups.
- Set up SSH key-based authentication.
- Configure sudo permissions for new users.
- Use **Ansible Roles** for better structure and reusability.

## 📁 Project Structure
```
ansible-user-management/
├── inventory/
│   ├── gcp.ini  # Inventory file with GCP instances
├── playbooks/
│   ├── manage_users.yml  # Main playbook to manage users
├── roles/
│   ├── manage_users/
│   │   ├── tasks/
│   │   │   ├── main.yml  # User management tasks
│   │   ├── files/
│   │   │   ├── pipelinestein.pub  # Public SSH key
├── README.md  # Project documentation
```

## 🛠 Prerequisites
Ensure you have the following installed:
- **Google Cloud SDK** (`gcloud` CLI)
- **Ansible** (`pip install ansible`)
- **SSH keys** generated (`ssh-keygen -t rsa -b 4096`)
- A configured GCP VM with SSH access

## 🔧 Setup and Usage

### 1️⃣ **Clone the Repository**
```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/ansible-user-management.git
cd ansible-user-management
```

### 2️⃣ **Set Up Inventory**
Edit `inventory/gcp.ini` and replace it with your instance details:
```ini
[gcp_servers]
instance-1 ansible_host=34.59.83.18 ansible_user=dreamfyre ansible_ssh_private_key_file=~/.ssh/google_compute_engine
```

### 3️⃣ **Run the Playbook**
Execute the user management playbook:
```bash
ansible-playbook -i inventory/gcp.ini playbooks/manage_users.yml
```

### 4️⃣ **Verify User Access**
Try SSH-ing into the new user account:
```bash
ssh -i ~/.ssh/pipelinestein pipelinestein@34.59.83.18
```

## 🔄 Updating Users
To modify users or add new SSH keys, update the relevant task files in `roles/manage_users/tasks/main.yml` and rerun the playbook.

## 📜 License
This project is open-source and licensed under the MIT License.

## 🤝 Contributing
Feel free to fork this repo, submit pull requests, or open issues for improvements!


