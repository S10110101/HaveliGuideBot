# HaveliGuideBot
This is a Haveli Guide Bot based on Telegram which can be used to gather vairous information about the havelis of lucknow .. 

Table of Contents
1. Introduction
2. Project Overview
3. System Architecture
4. Key Features
5. Technical Specifications
6. Implementation Details
7. Challenges & Solutions
8. Future Enhancements
9. Conclusion
    
**1. Introduction**
HaveliGuideBot is an innovative Telegram bot designed to provide immersive cultural experiences by delivering information about historical havelis (traditional mansions) in India. The bot features multi-language support with real-time translation and text-to-speech capabilities, making cultural heritage accessible to diverse audiences.
Project Goals:
•	Provide accessible heritage information
•	Support multiple languages (English, Hindi, Urdu)
•	Offer engaging multimedia content
•	Create intuitive user interactions
•	Handle large content within platform limitations

**2. Project Overview**
HaveliGuideBot enables users to:
1.	Select their preferred language
2.	Browse a paginated list of historical havelis
3.	View detailed information with images
4.	Listen to descriptions via text-to-speech
5.	Provide feedback on content quality

Key Components:
•	Telegram Bot Interface
•	JSON Data Repository (Havelis.json)
•	Translation Service (GoogleTranslator)
•	Text-to-Speech Engine (edge_tts)
•	Interactive Menu System

**3. System Architecture**
The system architecture represents how different components of HaveliGuideBot interact to deliver services:
1. User initiates interaction via Telegram
2. Bot processes request through handlers
3. Content retrieved from JSON dataset
4. Text translated to target language
5. Audio generated for descriptions
6. Multimedia response delivered to user

**4. Key Features**
4.1 Multi-language Support
•	Supported Languages: English, Hindi, Urdu
•	Natural language detection ("hindi", "हिंदी", "اردو")
•	Dynamic content translation
•	Persistent user language preference

4.2 Interactive Content Delivery
•	Paginated haveli lists (5 per page)
•	Image galleries with Markdown captions
•	Chunked descriptions (≤4000 characters)
•	Location links with map integration
•	On-demand audio descriptions

4.3 User Engagement Features
•	Thumbs up/down feedback system
•	Follow-up assistance prompts
•	Context-aware error handling
•	Session persistence for seamless experience

4.4 Administrative Features
•	Comprehensive error logging
•	Automatic resource cleanup
•	Markdown injection protection
•	Graceful degradation on API failures

**5. Technical Specifications**
Dependencies:
python-telegram-bot == 20.3
deep-translator == 1.11.4
edge-tts == 6.1.3
asyncio == 3.4.3

System Requirements:
•	Python 3.8+
•	Internet connectivity
•	Telegram API access
•	Temporary storage for audio files

Limitations:
•	Max caption length: 1,000 characters
•	Max message length: 4,000 characters
•	Max audio generation: 5 minutes

6. Implementation Details
Example Core Function:
async def send_haveli_content(index, context, chat_id, lang):
    # 1. Retrieve haveli data
    # 2. Translate content asynchronously
    # 3. Send image with formatted caption
    # 4. Send description in chunks
    # 5. Generate and deliver audio
    # 6. Request feedback

Content Processing Pipeline:
•	Text Sanitization: Escape Markdown special characters
•	Chunking Algorithm: Split text at sentence boundaries
•	Parallel Processing: Concurrent translation tasks
•	Audio Management: Temp file creation/deletion

State Management:
•	Selected language
•	Current search index
•	Translated haveli list
•	Last viewed haveli

**7. Challenges & Solutions**
The table below outlines key challenges encountered during development and their respective solutions:
Challenge	Solution
Telegram Message Limits	Implemented sentence-aware text chunking
Multilingual Audio	Mapped language codes to neural voices
Real-time Translation	Asynchronous processing with gather()
State Persistence	Context-based user data storage
Markdown Formatting Issues	Regex-based special character escaping
API Failure Handling	Graceful degradation with user alerts

**8. Future Enhancements**
Extended Language Support
•	Add Punjabi, Marwari, and Bengali
•	Community-driven translations
Enhanced Multimedia
•	360° virtual tours
•	Historical photographs gallery
•	Video documentaries
User Experience Improvements
•	Favorites/bookmarking system
•	Personalized recommendations
•	Visit planning tools
Administration Features
•	Feedback analytics dashboard
•	Content management system
•	Usage statistics monitoring
Technical Upgrades
•	Translation caching
•	CDN for media assets
•	Redis for session management

9. Conclusion
HaveliGuideBot successfully bridges cultural heritage with modern technology, offering an accessible platform for exploring historical architecture. By combining multilingual support with engaging multimedia features, the project demonstrates how technical solutions can enhance cultural preservation and education.

The bot's architecture showcases effective handling of platform limitations while delivering rich content experiences. With its modular design and scalable foundation, HaveliGuideBot provides a robust framework for future expansion into broader cultural heritage domains.
Project Impact:
•	Makes cultural heritage accessible to diverse audiences
•	Demonstrates practical NLP application
•	Provides template for similar cultural projects
•	Preserves historical knowledge digitally

Appendix A: Sample JSON Structure
{
  "Havelis": [
    {
      "name": "Patwon Ki Haveli",
      "description": "The most famous cluster of havelis in Jaisalmer...",
      "image": "https://example.com/patwon.jpg",
      "location": "Jaisalmer, Rajasthan",
      "location_link": "https://maps.app.goo.gl/example"
    }
  ]
}

Appendix B: Voice Mapping
voice_map = {
  "en": "en-US-AriaNeural",
  "hi": "hi-IN-SwaraNeural",
  "ur": "ur-PK-AsadNeural"
}

Appendix C: Command Reference
•	/start: Initialize bot interaction
•	Language keywords: "english", "hindi", "urdu"
•	Navigation: Next ➡️, Prev ⬅️
•	Feedback: 👍/👎

This document was generated on 2025-06-17
Project Repository: github.com/S10110101/HaveliGuideBot
Telegram Bot Link: https://t.me/HaveliGuideBot
@made by Shivang Agrawal
