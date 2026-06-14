#ARTIFICIAL INTELLIGENCE CHATBOT - AI BUILDERS BOOTCAMP BY VEDAM SCHOOL OF TECHNOLOGY-An AI-powered Career Coach Chatbot built using Python, Streamlit, Ollama, and Qwen 2.5. The application provides personalized career guidance, learning roadmaps, skill recommendations, college advice, and career planning support through a conversational interface.

    import streamlit as st
    import ollama
        
    st.title("AI Career Coach")
    
    question = st.text_input("Ask your career question")

    if st.button("Submit") and question:

    response = ollama.chat(
        model="qwen2.5:0.5b",
        messages=[
            {
                "role": "system",
                "content": """You are an expert career coach.
                Help students with:
                - Career choices
                - Colleges
                - Skills
                - Internships"""
            },
            {
                "role": "user",
                "content": question
            }
        ]
    )

    st.write(response["message"]["content"])
