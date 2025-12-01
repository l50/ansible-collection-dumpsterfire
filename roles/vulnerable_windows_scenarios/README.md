<!-- DOCSIBLE START -->
# vulnerable_windows_scenarios

## Description

Scenarios is a collection of vulnerable windows scenarios for use in training
and testing of cybersecurity tools and techniques.


## Requirements

- Ansible >= 2.14

## Role Variables

### Role Variables (main.yml)

| Variable | Type | Value | Description |
| -------- | ---- | ----- | ----------- |
| `vulnerable_windows_scenarios_sensitive_document_content` | str | `this is secret do not share with anyone 4f67650d0f81f138ba00675ea26cc9a4` | No description |
| `vulnerable_windows_scenarios_share_name` | str | `DATABOX` | No description |
| `vulnerable_windows_scenarios_users` | list | `[]` | No description |
| `vulnerable_windows_scenarios_users.0` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_users.0.name` | str | `PaigeTurner` | No description |
| `vulnerable_windows_scenarios_users.0.password` | str | `{{ lookup('ansible.builtin.password', '/dev/null', length=16, chars=['ascii_letters', 'digits', 'punctuation']) }}` | No description |
| `vulnerable_windows_scenarios_users.0.description` | str | `New User` | No description |
| `vulnerable_windows_scenarios_users.0.manager` | str | `Frank` | No description |
| `vulnerable_windows_scenarios_users.0.mentor` | str | `Sarah` | No description |
| `vulnerable_windows_scenarios_users.1` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_users.1.name` | str | `FrankFurter` | No description |
| `vulnerable_windows_scenarios_users.1.password` | str | `Password123!` | No description |
| `vulnerable_windows_scenarios_users.1.description` | str | `Description of the user` | No description |
| `vulnerable_windows_scenarios_users.1.manager` | str | `John` | No description |
| `vulnerable_windows_scenarios_users.1.mentor` | str | `Doe` | No description |
| `vulnerable_windows_scenarios_shares` | list | `[]` | No description |
| `vulnerable_windows_scenarios_shares.0` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_shares.0.name` | str | `DATABOX` | No description |
| `vulnerable_windows_scenarios_shares.0.path` | str | `C:\Resources` | No description |
| `vulnerable_windows_scenarios_shares.0.description` | str | `Resources Share` | No description |
| `vulnerable_windows_scenarios_shares.0.full_access` | list | `[]` | No description |
| `vulnerable_windows_scenarios_shares.0.full_access.0` | str | `PaigeTurner` | No description |
| `vulnerable_windows_scenarios_shares.1` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_shares.1.name` | str | `FSERVER01` | No description |
| `vulnerable_windows_scenarios_shares.1.path` | str | `C:\DeptFiles` | No description |
| `vulnerable_windows_scenarios_shares.1.description` | str | `Department Files Share` | No description |
| `vulnerable_windows_scenarios_shares.1.full_access` | list | `[]` | No description |
| `vulnerable_windows_scenarios_shares.1.full_access.0` | str | `Everyone` | No description |
| `vulnerable_windows_scenarios_documents` | list | `[]` | No description |
| `vulnerable_windows_scenarios_documents.0` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_documents.0.path` | str | `C:\Resources\attorney_client_privileged_intellectual_property.txt` | No description |
| `vulnerable_windows_scenarios_documents.0.content` | str | `{{ vulnerable_windows_scenarios_sensitive_document_content }}` | No description |
| `vulnerable_windows_scenarios_welcome_documents` | list | `[]` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.path` | str | `C:\DeptFiles\Welcome.txt` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user.name` | str | `PaigeTurner` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user.password` | str | `{{ lookup('ansible.builtin.password', '/dev/null', length=16, chars=['ascii_letters', 'digits', 'punctuation']) }}` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user.description` | str | `New User` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user.manager` | str | `Frank` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.user.mentor` | str | `Sarah` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share` | dict | `{}` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share.name` | str | `DATABOX` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share.path` | str | `C:\Resources` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share.description` | str | `Resources Share` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share.full_access` | list | `[]` | No description |
| `vulnerable_windows_scenarios_welcome_documents.0.share.full_access.0` | str | `PaigeTurner` | No description |

## Tasks

### documents.yml


- **Create documents** (ansible.windows.win_file)
- **Set content of documents** (community.windows.win_lineinfile)
- **Create and populate welcome document** (ansible.builtin.template)

### main.yml


- **Include tasks for user setup** (ansible.builtin.include_tasks) - Conditional
- **Include tasks for share setup** (ansible.builtin.include_tasks) - Conditional
- **Include tasks for document setup** (ansible.builtin.include_tasks) - Conditional

### shares.yml


- **Ensure directories for shares exist** (ansible.windows.win_file)
- **Create network shares** (ansible.windows.win_share)

### users.yml


- **Create users with provided details** (ansible.windows.win_user)

## Example Playbook

```yaml
- hosts: servers
  roles:
    - vulnerable_windows_scenarios
```

## Author Information

- **Author**: Jayson Grace
- **Company**: techvomit
- **License**: MIT

## Platforms


- Ubuntu: all
- macOS: all
- EL: all
- Windows: all
<!-- DOCSIBLE END -->
