 Our product is a part-time job matching app. It serves both job seekers and employers. Our platform has an intelligent matching system based on reinforcement learning. It learns job seekers' preferences，behavior and feedback to provide personalized service. There is a big demand for part-time job opportunities in the UK. But there has been a lack of a reliable, safe platform for employers and part-time job seekers. The part-time job market has always been ignored. So our product is designed to fill the huge gap in the market. Both employers and job seekers can register at our platform. Users can subscribe to our app for just £10 per month. 
 
   Firstly, job seekers register at our platform with their email or phone number. Their personal information, including age, gender, educational background, and work experience is required. Then job seekers upload identification documents and relevant materials. Our team will review the submission. Registration will be successfully completed after we approve the submission. After successfully registering, job seekers need to finish their preference settings. The settings include location, preferred job type (industry and role), available working hours, and expected salary. Our intelligent matching system needs the information to make judgements.
   
   Secondly, employers also register on our platform. Registration requires the company registration number, which is automatically verified with the Companies Information database. Our verification team will review the application. Limited functionality is available during the review. Full access will be granted when verification is completed. After completing the registration, the company needs to complete its profile, including a company introduction, geographical location, and contact details. Then the company can post job information, including salary standards, required skills, working time, and location requirements. Our intelligent matching system will match job seekers with employers' job requirements based on their information, behavior, and feedback. If a job seeker is interested in a position, they can contact the employer directly through our in-app chat system. Our platform will record all conversations in case potential disputes in the future.
   
 The core of our platform is intelligent matching system. The biggest challenge is how to accurately meet massive job-seeking demand. And we have a great amount of job seeker and job position data. So we use our self-developed recommendation model to achieve precise match. The foundation of our system is reinforcement learning. The reinforcement learning matching system regards job-seeker matching as a sequential decision-making process. The system works as an agent to learn the optimal policy in the complex environment. Each time the system recommends job opportunities to users. Users will give feedback and the intelligent system will adjust and optimize based on the users feedback. Each user has a buffer to store relevant information.
  
  We transform job preferences, user behavior, and feedback into computable data.Therefore we are able to evaluate the quality of decision through computation.   
Immediate rewards:  
View details: r = +0.1 (user shows interest in recommendation)  
Save job: r = +0.3 (demonstrates stronger interest)  
Apply for job: r = +0.5 (strong positive feedback)  
Ignore/quick swipe: r = -0.1 (signal of disinterest)  
Explicit rejection: r = -0.3 (negative feedback)  
Delayed rewards:  
Receiving interview: r = +1.0 (signal of match quality)  
Job offer: r = +2.0 (confirmation of high-quality match)  
Completing job term: r = +3.0 (long-term successful match)  
Early resignation: r = -1.0 (signal of matching problem) 

(1) Job Value Calculation Equation  
The total expected value of job position can be calculated by this equation:  

V = PI × (Vimmediate + Vdelayed × D)  

• V is the total expected value of the job position.   
• PI is the personalized interest factor (ranging from 0 to 1).   
• Vimmediate is the sum of expected immediate rewards.   
• Vdelayed is the sum of expected delayed rewards.   
• D is a discount factor for delayed rewards (0.7-0.9).  
(2) Components of Immediate Rewards  
Vimmediate = (Pview × 0.1) + (Psave × 0.3) + (Papply × 0.5) - (Pignore × 0.1) - (Preject × 0.3)  
• Pview is the probability the user will view details (0-1)   
• Psave is the probability the user will save the job (0-1)   
• Papply is the probability the user will apply for the job (0-1)   
• Pignore is the probability the user will ignore the job (0-1)   
• Preject is the probability the user will explicitly reject the job (0-1)  
(3) Components of Delayed Rewards  
Vdelayed = (Pinterview × 1.0) + (Pjob_offer × 2.0) + (Pcomplete × 3.0) - (Presign × 1.0)  
• Pinterview is the probability of receiving an interview (0-1)   
• Pjob_offer is the probability of receiving a job offer (0-1)   
• Pcomplete is the probability of completing the job term (0-1)   
• Presign is the probability of early resignation (0-1)  
(4) Personalized Interest Factor  
PI = (Wskill × Sskill + Wlocation × Slocation + Wtime × Stime + Wsalary × Ssalary) / (Wskill + Wlocation + Wtime + Wsalary)  
• Sskill is the skill match score (0-1)   
• Slocation is the location match score (0-1)   
• Stime is the time availability match score (0-1)   
• Ssalary is the salary match score (0-1)   
• W values are the weights for each factor based on user preferences  

Example:  
For a specific job and user:  
Skill match: 0.8, Weight: 0.4   Location match: 0.7, Weight: 0.3  
Time match: 0.9, Weight: 0.2   Salary match: 0.6, Weight: 0.1  
Probability of viewing: 0.6    Probability of saving: 0.4  
Probability of applying: 0.3   Probability of ignoring: 0.3  
Probability of rejecting: 0.1   Probability of interview: 0.2  
Probability of job offer: 0.15   Probability of completion: 0.1  
Probability of resignation: 0.05  
PI = (0.4×0.8 + 0.3×0.7 + 0.2×0.9 + 0.1×0.6) / (0.4 + 0.3 + 0.2 + 0.1) = 0.76  
Vimmediate = (0.6×0.1) + (0.4×0.3) + (0.3×0.5) - (0.3×0.1) - (0.1×0.3) = 0.06 + 0.12 + 0.15 - 0.03 - 0.03 = 0.27  
Vdelayed = (0.2×1.0) + (0.15×2.0) + (0.1×3.0) - (0.05×1.0) = 0.2 + 0.3 + 0.3 - 0.05 = 0.75  
V = 0.76 × (0.27 + 0.75 × 0.8) = 0.76 × (0.27 + 0.6) = 0.76 × 0.87 = 0.66  
The final value of 0.66 is the expected value of this position to this user. Our match system will prioritize the position with higher values.

This is our core algorithm model. We use complex calculations to determine the value of each position for job seekers based on the above actions. By ranking them , we can recommend job positions to job seekers in order.We transform the abstract decision-making process into concrete.  This process is scientific and efficient.

Analysis

We confirm that this product may have a huge impact in the future through a variety of different path analysis, the main analysis process is as follows:

Market Trend Analysis

We looked at recent UK job market reports and government data, and we found that the demand for flexible work models and part-time jobs has increased significantly in recent years. With the transformation of economic structure and work patterns after the pandemic, more and more people tend to seek part-time or temporary jobs to meet the needs of life flexibility and income diversification. At the same time, employers are increasingly adopting hiring methods that reduce fixed labor costs, which provides a growing market base for part-time matching services.
The demand for part-time job seekers in the UK has long been overlooked, and our product are designed to fill this market gap.

1：The UK employment rate for people aged 16 to 64 years was estimated at 74.9% in October to December 2024. This is above estimates of a year ago, and up in the latest quarter.
The UK unemployment rate for people aged 16 years and over was estimated at 4.4% in October to December 2024. This is above estimates of a year ago, and up in the latest quarter.
The UK economic inactivity rate for people aged 16 to 64 years was estimated at 21.5% in October to December 2024. This is below estimates of a year ago, and down in the latest quarter.
Labour market overview, UK - Office for National Statistics
2：More than a quarter of working adults in Great Britain (28%) were hybrid working in the autumn of 2024. While the trend in working only from home has fallen since 2021, a hybrid-working model (part travelling to work, and part at home), has become the ‘new normal’ for around a quarter of workers.
Who are the hybrid workers? - Office for National Statistics

Competitor Analysis and Service Gaps

We conducted a detailed analysis of popular part-time job platforms in the UK (such as Indeed and Reed) and found that most platforms still rely on traditional keyword matching and static filtering methods. They cannot respond dynamically to user behavior and personalized needs. In contrast, we plan to use a reinforcement learning (RL) recommendation system, allowing the app to continuously optimize matching strategies based on real-time user feedback and basic information, providing more precise job recommendations. This technical advantage will fill the gap in personalized services on existing platforms and significantly enhance our product's market competitiveness.

1: Advantages of Reinforcement Learning (RL):

RL can iterate and optimize recommendations based on user feedback (e.g., swiping behavior, application rate, and satisfaction after hiring), making it an ideal choice for dynamic and preference-driven markets like part-time work.

2: UK Employees Environment and Technological Readiness

The smartphone penetration rate in the UK is very high (87%), and open banking APIs support seamless integration of user data (skills, location, availability) to train RL models.

Technical Feasibility and Advanced Validation

In addition, according to relevant academic studies and industry cases, reinforcement learning has achieved remarkable results in recommendation systems in the fields of film and TV, retail and e-commerce, and its adaptive and continuous learning characteristics can greatly improve the accuracy of personalized matching and user satisfaction. These successful precedents provide a solid theoretical and practical basis for applying this technology to part-time job matching.

Pricing Model Design

Our pricing model is very simple, adopting a monthly subscription fee of £10. Users pay a fixed monthly fee to enjoy all the services offered by the product, including job recommendations, personalized career advice and full access to employer information. This pricing strategy ensures the stability of our revenue, while also lowering the user barrier to use, which can attract more users in the initial stage.

Conclusion

Through a analysis of market trends, service gaps, user needs and technical feasibility, we believe that developing a part-time job matching app based on reinforcement learning not only meet the growing demand for flexible employment, but also has obvious competitive advantages. We believe that this will be a very promising business opportunity.

2 Market  
2.1 Market Assumptions and Key Pain Points  
A key part of market validation is realizing that our business idea depends on guesses about what customers want, how big the market is, and how much they will pay. By clearly stating these guesses early, we can plan tests to reduce our risk (Ries, 2011).

Who Is Our Customer?  
Our part-time job matching app targets two main customer segments:  
1.	Job Seekers: Typically, individuals with limited availability (e.g., university students or those supplementing a main income) who find general job sites oversaturated with full-time listings. They are motivated by the desire for a trustworthy, convenient solution that reduces the search time for legitimate part-time roles (Office for National Statistics, 2025).
2.	Employers: Often local cafés, retailers, and small companies with high turnover in casual roles. These employers are seeking a cost-effective, user-friendly platform to quickly access verified candidates without incurring large recruitment fees (CIPD, 2025).

What Problems Are We Solving (Pain Points)?  
1.	Mainstream job sites do not filter effectively for part-time positions, leading to wasted time for both parties. Additionally, job seekers worry about scams or unverified postings, while employers fear unqualified applicants.  
2.	Traditional recruitment is time-consuming and expensive, particularly for small and medium-sized enterprise (SME) looking to fill short shifts or seasonal roles (CIPD, 2025).  
3.	Both groups report frustration with cluttered interfaces, limited personalization, and having to manually filter out irrelevant full-time jobs (Fitzpatrick, 2013).  

How Many Customers? Market Value?  
In the UK, more than 8 million people work part-time, making up about 33% of the workforce (Office for National Statistics, 2025). There are also around 5.5 million small and medium-sized businesses (SMEs), many of which depend on part-time workers to handle changing workloads (Federation of Small Businesses, 2024). This means the market is quite large, and even getting a small share of it could make the business profitable, especially with a subscription model like £10 per month per user.

Is the Market Saturated?
Most job websites cover all types of jobs, but none focus specifically on verified part-time positions with a smart matching system. Big platforms target a wide range of users, which leaves a gap for a specialized service that caters directly to part-time job seekers and employers.

Market Risks and Opportunities  
Risks:  
1.	If the subscription fee is deemed too high or if users find insufficient job opportunities early on, they may abandon the platform.  
2.	Compliance with privacy and data protection (GDPR) is critical, as sensitive personal data is collected.  
3.	Downturns could reduce the availability of part-time jobs or the hiring capacity of SMEs.  
Opportunities:  
1.	Remote and on-demand roles are increasingly popular, boosting part-time labour demand (ONS, 2025).  
2.	Reinforcement learning provides a unique selling point, allowing for continuous improvement in matching algorithms.  
3.	Collaborating with universities or college career centres could channel a large pool of motivated part-time job seekers directly to our platform.  

2.2 Secondary Research  
We started by looking at official reports and reliable data to check our ideas about market size, types of users, and common problems. The Office for National Statistics (2025) shows that more people, especially students and parents, are looking for flexible jobs as they manage other responsibilities. A study by the Chartered Institute of Personnel and Development (2025) also found that small businesses struggle to hire part-time workers because of high costs, long hiring processes, and unqualified applicants. 

To understand the market size, we looked at industry data from the Federation of Small Businesses (2024). Although the report does not focus only on part-time jobs, it shows that small businesses regularly need workers for shorter hours. Many of these businesses cannot afford the high costs of using hiring agencies. This supports our idea that a specialized platform could help fill this gap in the market.

Looking at global trends, more people are choosing flexible work options to improve their work-life balance. Since the pandemic, part-time, project-based, and gig jobs have become more common (McKinsey, 2021). This growing demand shows that our platform could have the potential to expand beyond the UK in the future.

2.3 Primary Research
Building on our secondary research, we conducted interviews and online surveys to verify real-world sentiment and test our assumptions regarding willingness to subscribe (Fitzpatrick, 2013). A short online questionnaire was posted on Reddit, WhatsApp groups, and via student email, yielding over 80 responses in one week:

Job Seekers’ Perspective
1.	Over 65% of respondents cited frustration with irrelevant postings on mainstream sites. Roughly half expressed concern over unverified employers or potential scams.
2.	Approximately 60% of respondents were open to paying £5–£10 per month if it substantially reduced time spent job hunting and guaranteed trustworthy postings.

Employers’ Perspective
1.	In follow-up interviews with seven SMEs (local shops and cafés), owners voiced concerns about high turnover and the cost of placing ads on large sites. They frequently complained of receiving too many low-quality applications, indicating a strong need for targeted recruiting channels.
2.	Most owners welcomed a system that would verify both job seekers and businesses, further implying that trust could be a major selling point.
These findings validate our hypothesis that personalization and safety are top priorities in the UK part-time job market, and they reinforce the value of an intelligent recommendation approach. They also confirm that a modest subscription fee would be acceptable to a significant portion of our user base if paired with genuine value-add features—primarily better matching, faster discovery of relevant roles, and reduced recruitment friction.

Competitors Market  
Indeed  
Indeed is the biggest online recruitment website in the market in the UK, although they were founded in America in 2004 and do operate globally in over 60+ countries. With over 595 million job seekers on their site along with 3.5 million employers using it to hire workers. They have diversified their offerings quite a bit from just being a basic job site over the years. They offer other options such as career advice for job seekers looking to get into a particular industry (i.e. recommending courses to partake in), this was introduced in 2017. Due to the recent Artificial Intelligence (AI) boom in 2023, Indeed have also began to incorporate AI elements in their services. Indeed was using AI since it was founded but this recent inclusion of OpenAI GPT models has made it much more accurate, efficient and performative. On the employer side of things, they have added features which use AI to benefit them such as ‘Indeed’s AI Job Description Generator’ which creates captivating descriptions which compel candidates to apply. They have also added a feature called ‘Candidate Highlights’ which analyses and summarizes each candidates resume to suggest why they may be fit for the role and point out areas in which they are not. 
We consider Indeed to be a direct competitor to us. Our solution is primally fixated on the part-time job market while they operate in both full-time and part-time. Due to them operating in a large variety of countries their job pool for remote part-time work may also be bigger than ours. They are also ahead of us with their collaboration with OpenAI and are using AI to enhance their multitude of services. All of these are strengths for Indeed, however they are not without weaknesses. While Indeed do offer the ability for employers to post free job postings for certain roles (with the caveat that the post loses visibility as newer jobs are added to the site), sponsored job postings are much more lucrative when you are not in a hurry to find someone quick but rather your looking for someone who is experienced and reliable. Additionally, employers must pay a monthly/yearly subscription to access the huge database of resumes that Indeed offers (Indeed Smart Sourcing). Hence, there is a cost for the employer when using Indeed, this can pile up when you a big company with multiple roles especially part-time roles where people may leave suddenly due to a lack of progression on offer. So, although Indeed may have a huge amount of strengths there are also weaknesses which limit how lucrative it is in the part-time job market for big and small businesses and our solution is cheaper to use for businesses.
Reed  
Reed is an employment agency that is based in the UK, and while they are an employment agency their website established in 1995 was the UK’s first online recruitment website. Reed has roles from almost 19,000 recruiters a year, and over 100 million workers use Reed to search for roles. Like Indeed, Reed has diversified their services, with having courses available from learning providers and advertise more than 155,000 courses on a variety of subjects. They also have career advice available for people looking for expert tips and advice on resumes, cover letters and interviews. In terms of AI Reed seems to have embraced it in a limited manner. Via a collaboration with Kortical, the only integration of AI that Reed uses is a chatbot (ChatGPT) used for helping employers post jobs on their site. Reed also plans on expanding the use of AI to create knowledge-based bots for internal FAQs and other areas, though it does not seem like Reed has a big focus on AI like Indeed or LinkedIn.
Reed is another direct competitor to us. They operate in the part-time and full-time job market (like Indeed); however, they only operate in the UK, so the pool for part time work will be the same as us. Reed’s integration of AI is limited in the sense that it does not cut the work needed for recruiters, they still need to manually do the work to post job listings on their website. Our solution is more focused on the job seekers side, and we believe that AI has more use here, than on the recruiter side. Another weakness for Reed is the cost of using it, they do not offer fully free job postings, and you can not search the resume database for free like Indeed. The cost of using it compared to Indeed depends on the size of the business and can vary but in most cases they’re similar. Again, this limits Reed in how effective it is in the part-time job market, and we believe our solution is much more lucrative in this sense. Overall, Reed is a direct competitor that has more weaknesses than Indeed when competing against us. 
LinkedIn   
LinkedIn is a business and employment-focused online social media platform that was founded in America in 2003, that was later bought by Microsoft in 2016. It is mainly used for networking and offers the ability for employers to post role vacancies and job seekers to post their CV. The platform has more than 1 billion members in 200 countries and regions worldwide. LinkedIn uses AI in several ways both on job seekers and business side, as they use GenAI, machine learning and OpenAI models. There is an AI-powered writing assistant that can assist recruiters in writing job descriptions and help personalize follow ups to an application from a certain user based on their data and skills. There is a similar tool on the job seekers side that helps users build their profiles with personalized writing suggestions based on their writing style. They also use AI-assisted search to help recruiters search for candidates based on their instructions reducing time spent for recruiters. AI is used in a laxer way in content suggestions for users and message templates for certain messages. LinkedIn also use AI to extract information from posts in a user’s feed to train their AI models, an asset with the number of users they have. 
In our eyes LinkedIn is more of an indirect competitor to us. They operate in both the part-time and full-time job market. We view LinkedIn as more of a networking site for professionals and less of an actual recruitment website. The main goal of LinkedIn is networking and staying informed about the industry that you are in. Out of 1 billion members only 40 million people search LinkedIn for jobs every week globally.  Their usage of AI is more advanced than ours, helping both the recruiter and job seeker so that’s a strength for them in that aspect. While LinkedIn offers a free job posting the post is only active for 21 days. You can pay to promote your job post, however the actual cost of doing so ranges from $10 to $500 with extra fees for other features. All these other features require a quote from LinkedIn to use based on what company is requesting to use them. This is a weakness as businesses without LinkedIn presence are not going to pay these costs just to be able to get the most out of the site. Even if you are a business that has LinkedIn depending on your size these costs can increase greatly as your company grows. Our solution allows for businesses to freely post ads making it cheaper for start ups and even big businesses. LinkedIn also does not offer a resume database rather employers can only view candidates profiles. This is another weakness and further makes our solution much more appealing for businesses to use. LinkedIn is a formidable indirect competitor that we are not worried about, as our product aims to address the part-time job market, that may not have a huge presence on LinkedIn. 


