import streamlit as st

st.set_page_config(page_title="Phishing Awareness", layout="centered")

st.title("Phishing Awareness Module")

st.header("What is Phishing?")
st.write("""
Phishing is a cyber attack where attackers trick users into revealing sensitive information 
like passwords, bank details, or personal data by pretending to be a trusted source.
""")

st.header("How to Recognize Phishing Emails")
st.write("""
- Suspicious sender email address
- Urgent or threatening messages
- Spelling and grammar mistakes
- Unknown attachments or links
""")

st.header("Fake Websites Warning Signs")
st.write("""
- URL looks slightly different (e.g., g00gle.com)
- No HTTPS (no lock symbol)
- Poor design or broken links
""")

st.header("Social Engineering Tactics")
st.write("""
Attackers manipulate emotions like fear, urgency, or curiosity.
Examples:
- "Your account will be blocked!"
- "Click here to win a prize!"
""")

st.header("Example of Phishing Message")
st.code("""
Subject: Urgent! Your bank account is locked

Dear user,
Click the link below to verify your account immediately:
http://fake-bank-login.com
""")

st.header("How to Stay Safe")
st.write("""
- Never click suspicious links
- Verify sender before responding
- Use strong passwords
- Enable 2-factor authentication
""")

st.header("Quick Quiz")

q1 = st.radio(
    "1. What is a sign of phishing email?",
    ("Professional design", "Urgent message", "Official logo")
)

q2 = st.radio(
    "2. Which URL is suspicious?",
    ("https://google.com", "https://g00gle.com", "https://amazon.com")
)

score = 0

if st.button("Submit Quiz"):
    if q1 == "Urgent message":
        score += 1
    if q2 == "https://g00gle.com":
        score += 1

    st.success(f"Your Score: {score}/2")

    if score == 2:
        st.success("Excellent! You understand phishing well.")
    else:
        st.warning("Learn more to stay safe online!")
