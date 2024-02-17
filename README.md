# Cybersecurity-chatbot-
This is a prototype project 
import random
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

nltk.download("punkt")
nltk.download("stopwords")

def preprocess_input(input_text):
    stop_words = set(stopwords.words("english"))
    words = word_tokenize(input_text.lower())
    words = [word for word in words if word.isalnum() and word not in stop_words]
    return " ".join(words)

def threat_detection(input_text):
    threats = ["malware", "virus", "phishing", "ransomware", "data breach", "hacker"]
    for threat in threats:
        if threat in input_text:
            return True
    return False

class PersonalInformationSecurityTools:
    @staticmethod
    def data_encryption():
        return "Data Encryption tools ensure that your data is secure by converting it into unreadable code."

    @staticmethod
    def password_manager():
        return "Password Managers help you generate and store strong, unique passwords for your accounts."

    @staticmethod
    def VPN():
        return "A Virtual Private Network (VPN) encrypts your internet connection, enhancing your online privacy."

    @staticmethod
    def secure_messaging_apps():
        return "Secure Messaging Apps offer end-to-end encryption for your conversations, ensuring they remain private."

    @staticmethod
    def secure_file_sharing():
        return "Secure File Sharing tools let you share sensitive files with others securely and without unauthorized access."

    @staticmethod
    def privacy_browser():
        return "Privacy Browsers focus on blocking trackers and enhancing your online privacy while browsing."

    @staticmethod
    def secure_cloud_storage():
        return "Secure Cloud Storage services ensure your files are stored safely in the cloud, protected with encryption."

    @staticmethod
    def identity_theft_protection():
        return "Identity Theft Protection services monitor your personal information online and offer alerts for potential breaches."

    @staticmethod
    def encrypted_communication():
        return "Encrypted Communication tools enable secure communication channels, safeguarding your conversations."

    @staticmethod
    def digital_privacy_tools():
        return "Digital Privacy Tools help you manage and protect your online presence, minimizing data exposure."

class InformationSecurityPrinciples:
    @staticmethod
    def confidentiality():
        return "Confidentiality ensures that sensitive information is only accessible to authorized individuals."

    @staticmethod
    def integrity():
        return "Integrity ensures that data remains accurate and unaltered during storage, transmission, and processing."

    @staticmethod
    def availability():
        return "Availability ensures that information and services are available and accessible when needed."

    @staticmethod
    def authentication():
        return "Authentication verifies the identity of users and ensures that only authorized users gain access."

    @staticmethod
    def authorization():
        return "Authorization grants appropriate permissions to authorized users based on their roles."

    @staticmethod
    def non_repudiation():
        return "Non-repudiation prevents individuals from denying their actions or transactions."

    @staticmethod
    def principle_of_least_privilege():
        return "The Principle of Least Privilege ensures that users are granted only the minimum access necessary."

    @staticmethod
    def defense_in_depth():
        return "Defense in Depth involves multiple layers of security to protect against various threats."

    @staticmethod
    def security_by_design():
        return "Security by Design integrates security measures throughout the development lifecycle."

    @staticmethod
    def continuous_monitoring():
        return "Continuous Monitoring involves ongoing assessment of security controls and threats."

def security_tips():
    tips = [
        "Use strong and unique passwords for all accounts.",
        "Enable two-factor authentication (2FA) wherever possible.",
        "Avoid clicking on suspicious links in emails or messages.",
        "Keep your software and operating system up to date.",
        "Regularly backup your data to a secure location.",
        "Be cautious when sharing sensitive information online.",
    ]
    return random.choice(tips) 
def define_cyber():
     cyber=[
            "Cybersecurity refers to the practice of safeguarding digital systems, networks, and sensitive information from unauthorized access, attacks, and potential threats. It involves the implementation of various tools, principles, and best practices to protect data integrity, confidentiality, and availability. The code snippet you provided demonstrates a cybersecurity chatbot designed to assist users in understanding and addressing potential security risks, offering information security principles, personal information security tools, incident response guidelines, and more."
     ]
     return "Here is the defintion:\n" + "\n".join(cyber)

def incident_response():
    return "In case of a cybersecurity incident, immediately disconnect from the internet and report it to your IT department or security team."

def antivirus_apps():
    apps = [
        "Norton Antivirus",
        "McAfee Antivirus",
        "Avast Antivirus",
        "Bitdefender Antivirus",
        "Kaspersky Antivirus",
        "Avira Antivirus",
        "Trend Micro Antivirus",
    ]
    return "Here are some popular antivirus apps:\n" + "\n".join(apps)

def legal_approach():
    approach =[
        "National Cyber Crime Reporting Portal",
        "Description: The official platform to report cybercrimes in India",
        "URL: https://cybercrime.gov.in/",
        "",
        "Local Police Station",
        "Description: You can report cybercrimes at your local police station as well.",
        "",
        "Indian Computer Emergency Response Team (CERT-In)",
        "Description: CERT-In handles cybersecurity incidents and provides assistance.",
        "Contact:",
        "Email: incident@cert-in.org.in",
        "Phone: 1800-11-4949"
    ]
    return "Here are some methods to report a cybercrime:\n" + "\n".join(approach)

def cybersecurity_chatbot():
    print("Chatbot: Hi! I am your cybersecurity assistant. How can I help you today? (type 'exit' to end)")

    report_keywords = [
        "report a cyber crime",
        "report cyber crime",
        "reporting a cyber crime",
        "reporting cyber crime"
    ]

    while True:
        user_input = input("You: ")  # Replace with appropriate input method for Android
        if user_input.lower() == "exit":
            print("Chatbot: Goodbye! Stay safe online.")
            break

        processed_input = preprocess_input(user_input)
        
        if threat_detection(processed_input):
            print("Chatbot: I detected a potential security threat in your input.")
            print("Chatbot: Please be cautious and avoid sharing sensitive information.")
        elif "data privacy measures" in processed_input:
            print("Chatbot: Here are some Personal Information Security tools:")
            print(PersonalInformationSecurityTools.data_encryption())
            print(PersonalInformationSecurityTools.password_manager())
            print(PersonalInformationSecurityTools.VPN())
            print(PersonalInformationSecurityTools.secure_messaging_apps())
            print(PersonalInformationSecurityTools.secure_file_sharing())
            print(PersonalInformationSecurityTools.privacy_browser())
            print(PersonalInformationSecurityTools.secure_cloud_storage())
            print(PersonalInformationSecurityTools.identity_theft_protection())
            print(PersonalInformationSecurityTools.encrypted_communication())
            print(PersonalInformationSecurityTools.digital_privacy_tools())
        elif any(keyword in processed_input for keyword in ["report","legal"]):
            print("Chatbot:", legal_approach())
        elif any(keyword in processed_input for keyword in ["tips", "best practices"]):
            print("Chatbot:", security_tips())
        elif any(keyword in processed_input for keyword in ["what","define"]):
            print("Chatbot:", define_cyber())
        elif any(keyword in processed_input for keyword in ["incident", "breach"]):
            print("Chatbot:", incident_response())
        elif "apps" in processed_input:
            print("Chatbot:", antivirus_apps())
        elif "principles" in processed_input:
            print("Chatbot: Here are some information security principles:")
            print(InformationSecurityPrinciples.confidentiality())
            print(InformationSecurityPrinciples.integrity())
            print(InformationSecurityPrinciples.availability())
            print(InformationSecurityPrinciples.authentication())
            print(InformationSecurityPrinciples.authorization())
            print(InformationSecurityPrinciples.non_repudiation())
            print(InformationSecurityPrinciples.principle_of_least_privilege())
            print(InformationSecurityPrinciples.defense_in_depth())
            print(InformationSecurityPrinciples.security_by_design())
            print(InformationSecurityPrinciples.continuous_monitoring())
        else:
            print("Chatbot:I'm sorry, I'm not sure how to assist you with that. Please ask another question.")
if __name__ == "__main__":
    cybersecurity_chatbot()
