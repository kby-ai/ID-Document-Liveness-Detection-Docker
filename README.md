<p align="center">
  <a href="https://play.google.com/store/apps/dev?id=7086930298279250852" target="_blank">
    <img alt="" src="https://github-production-user-asset-6210df.s3.amazonaws.com/125717930/246971879-8ce757c3-90dc-438d-807f-3f3d29ddc064.png" width=500/>
  </a>  
</p>

### Our facial recognition algorithm is globally top-ranked by NIST in the FRVT 1:1 leaderboards. <span><img src="https://github.com/kby-ai/.github/assets/125717930/bcf351c5-8b7a-496e-a8f9-c236eb8ad59e" alt="badge" width="36" height="20"></span>  
[Latest NIST FRVT evaluation report 2024-12-20](https://pages.nist.gov/frvt/html/frvt11.html)  

![FRVT Sheet](https://github.com/user-attachments/assets/16b4cee2-3a91-453f-94e0-9e81262393d7)

#### 🆔 ID Document Liveness Detection - Linux - [Here](https://web.kby-ai.com)  <span><img src="https://github.com/kby-ai/.github/assets/125717930/bcf351c5-8b7a-496e-a8f9-c236eb8ad59e" alt="badge" width="36" height="20"></span>
#### 🤗 Hugging Face - [Here](https://huggingface.co/spaces/kby-ai/IDCardRecognition)
#### 📚 Product & Resources - [Here](https://github.com/kby-ai/Product)
#### 🛟 Help Center - [Here](https://docs.kby-ai.com)
#### 💼 KYC Verification Demo - [Here](https://github.com/kby-ai/KYC-Verification-Demo-Android)
#### 🙋‍♀️ Docker Hub - [Here](https://hub.docker.com/r/kbyai/idl)

# ID-Document-Liveness-Detection-Docker

## Introduction

This repo demonstrates the server-based ID document liveness detection (anti-spoofing) capabilities for `ID card`, `passport`, and `driver's license`.<br/>
Our `ID document liveness detection SDK`(ID document anti-spoofing) suite effectively prevents common presentation attacks: `Screen Replay Attacks`, `Printed Copy Attacks`, and `Portrait Substitution Attacks`.

### ◾ID Card Recognition Product List
  | No.      | Repository | Release Type |
  |------------------|------------------|------------------|
  | 1        | [ID Card Recognition - Android](https://github.com/kby-ai/IDCardRecognition-Android)    | Android |
  | 2        | [ID Card Recognition - iOS](https://github.com/kby-ai/IDCardRecognition-iOS)    | iOS |
  | 3        | [ID Card Recognition - Flutter](https://github.com/kby-ai/IDCardRecognition-Flutter)    | Flutter |
  | 4        | [ID Auto Capture - React](https://github.com/kby-ai/ID-document-capture-React)    | Web Front-end |
  | 5        | [ID Card Recognition - Windows](https://github.com/kby-ai/IDCardRecognition-Windows)        | Server-Windows |
  | 6        | [ID Card Recognition - Linux](https://github.com/kby-ai/IDCardRecognition-Docker)        | Server-Linux |
  | 7        | [ID Card Recognition - C#](https://github.com/kby-ai/IDCardRecognition-CSharp-.NET)        | Server-Windows |
  | ➡️        | <b>[ID Card Liveness Detection - Linux](https://github.com/kby-ai/ID-Document-Liveness-Detection-Docker)</b>        | <b>Server-Linux</b> |

## Docker Run
- Pull docker image.
```bash
sudo docker pull kbyai/idl:latest
```
- Run docker container with license key file.
```bash
sudo docker run -v ./license.txt:/root/kby-ai-idl/license.txt -p 7860:7860 -p 9005:9000 kbyai/idl:latest
```
    
## SDK License

This Docker image utilizes `KBY-AI`'s `SDK`, which requires a license for each machine or instance on which it runs.
- To get the machine code (`HWID`) for license, use the following syntax:
```bash
sudo docker run -e LICENSE="xxxxx" kbyai/idl:latest
```
- To request the license, please provide us with the machine code (`HWID`) obtained from your console.
![image](https://github.com/user-attachments/assets/fed93cb2-a744-42fc-b0a2-964dfeeec52b)

## Contact us:</br>
🧙`Email:` contact@kby-ai.com</br>
🧙`Telegram:` [@kbyaisupport](https://t.me/kbyaisupport)</br>
🧙`WhatsApp:` [+19092802609](https://wa.me/+19092802609)</br>
🧙`Discord:` [KBY-AI](https://discord.gg/CgHtWQ3k9T)</br>
🧙`Teams:` [KBY-AI](https://teams.live.com/l/invite/FBAYGB1-IlXkuQM3AY)</br>

## Test API in KBY-AI Online Demo Page
  You can test the `SDK` against static image [here](https://web.kby-ai.com).</br>  
  ![image](https://github.com/user-attachments/assets/e803f57e-63dc-4c72-9994-13debed916ef)
  
## Test API with Gradio Demo
  To test the `Gradio` demo from the Docker image, access it at [http://127.0.0.1:7860](http://127.0.0.1:7860) or [http://localhost:7860](http://localhost:7860).
  
<img alt="Gradio Demo" src="https://github.com/user-attachments/assets/ccbbe118-5522-41e5-86f2-2b0b7854cfa0" width=1000/>

## API Instruction

`API` can be tested through `Postman` based on the following `endpoint` details.</br>
### 1. Processing Image with File
- `API` endpoint: `<base URL>/process_image`
- Method: `POST`
- Content-type: `multipart/form-data`
- Request Parameters:
  | Parameter      | Type | Description |
  |------------------|------------------|------------------|
  | image        | File | ID document image file with `*.jpg` or `*.png` extension |
- Request example</br>
![image](https://github.com/user-attachments/assets/97516d98-06ce-4f20-acd6-04ae942a3ad0)
### 2. Processing with Base64-Encoded String
- `API` endpoint: `<base URL>/process_image_base64`
- Method: `POST`
- Content-type: `application/json`
- Request Parameters: </br>
  | Parameter      | Type | Description |
  |------------------|------------------|------------------|
  | base64        | String | The base64-encoded string of the ID document image |
- Request example</br>
![image](https://github.com/user-attachments/assets/7a3ba967-8c44-43b0-bf9d-2af33a5a2be1)

## API Response Description in JSON
### 1. portraitReplace:
- Type: `Float`
- Description: A score indicating the likelihood that the portrait on the ID document has been tampered with or replaced. Higher values (closer to 1) suggest the portrait is likely original, while lower values may indicate potential tampering.</br>
### 2. printedCopy:
- Type: `Float`
- Description: A score that assesses whether the document is a printed copy rather than an original document. Values close to zero suggest the document might be a printed copy, while higher values indicate originality.</br>
### 3. screenReply:
- Type: `Float`
- Description: A score that determines if the document was displayed on a screen rather than being a physical ID. Lower values (closer to zero) imply a higher likelihood that the document is displayed on a screen.</br>
### 4. Result status:
- Type: `String`
- Description: Indicates the status of the liveness check on the document. "Ok" typically means that the document passed initial verification. Other statuses could indicate different levels of authenticity or potential issues with the document.</br>
- Status: `Ok`, `Too close to camera!`, `Too close to border!`, `Document cropped!`, `Too small!`, `Multiple documents`, `Is Colorless!`, `Document not found!`, `Unknown`
- Resonpse Example:
```json
{
    "result": {
        "portraitReplace": 0.590566158294678,
        "printedCopy": 2.0435e-11,
        "screenReply": 0.002031173091382,
        "status": "Ok"
    },
    "resultCode": "Ok"
}
```
