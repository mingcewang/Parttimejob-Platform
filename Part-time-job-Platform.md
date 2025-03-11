 Our product is a part-time job matching app. It serves both job seekers and employers. Our platform has an intelligent matching system based on reinforcement learning. It learns job seekers' preferences，behavior and feedback to provide personalized service. There is a big demand for part-time job opportunities in the UK. But there has been a lack of a reliable, safe platform for employers and part-time job seekers. The part-time job market has always been ignored. So our product is designed to fill the huge gap in the market. Both employers and job seekers can register at our platform. Users can subscribe to and use our app for just £10 per month. 
 
   Firstly, job seekers register at our platform with their email or phone number. Their personal information, including age, gender, educational background, and work experience is required. Then job seekers upload identification documents and relevant materials. Our team will review the submission. Registration will be successfully completed after we approve the submission. After successfully registering, job seekers need to finish their preference settings. The settings include location, preferred job type (industry and role), available working hours, and expected salary. Our intelligent matching system needs the information to make judgements.
   
   Secondly, employers also register on our platform. Registration requires the company registration number, which is automatically verified with the Companies House database. Our verification team will review the application. Limited functionality is available during the review. Full access will be granted when verification is completed. After completing the registration, the company needs to complete its profile, including a company introduction, geographical location, and contact details. Then the company can post job information, including salary standards, required skills, working time, and location requirements. Our intelligent matching system will match job seekers with employers' job requirements based on their information, behavior, and feedback. If a job seeker is interested in a position, they can contact the employer directly through our in-app chat system. Our platform will record all conversations in case potential disputes in the future.
   
     The core of our platform is intelligent matching system. The biggest challenge is how to accurately meet massive job-seeking demand. And we have a great amount of job seeker and job position data. So we use our self-developed recommendation model to achieve precise match. The foundation of our system is reinforcement learning. The reinforcement learning matching system regards job-seeker matching as a sequential decision-making process. The system works as an agent to learn the optimal policy in the complex environment. Each time the system recommends job opportunities to users. Users will give feedback and the intelligent system will adjust and optimize based on the users feedback. Each user has a buffer to store relevant information.
  
  We transform job preferences, user behavior, and feedback into computable data.
Therefore we are able to evaluate the quality of decision through computation.   
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

This is our core algorithm model. We use complex calculations to determine the value of each position for job seekers based on the above actions. By ranking them , we can recommend job positions to job seekers in order. This process is scientific and efficient.

