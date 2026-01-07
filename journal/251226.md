# 2025-12-26 Log — Project: Individual Sales Data Filtering

## 📌 Context
In the original design, the filter was built to display data from the **previous month**, because the Sales Department typically needs to handle correction data from that period. 

Today, however, the end users changed their request and asked for the filter to show the **current month** instead. This shift in requirements introduced inconsistency in the filtering logic and made it difficult to maintain stability.

## 👥 Stakeholders
- End users from the Sales Department  
- Translator (to confirm and clarify requirements)

## ⚠️ Problem
The end user changed their previous requirement:  
- Initially, they requested the filter to show **previous month** data for corrections.  
- Now, they want the filter to show **current month** data.  
This change caused confusion because their daily logic seems inconsistent, and requirements are not stable.

## 🔧 How I Handled It
- Captured the previous requirement for reference.  
- Asked the translator to confirm the meaning and remind the end user of what was agreed before.  
- Updated the filter logic according to the new request, even though it conflicted with earlier requirements.  
- Avoided questioning the end user directly, since requests must be accepted as given.

## 🛠️ Environment
- Web application filter logic  
- Sales data correction workflow  
- Communication via translator

## 🖼️ Supporting Images
![screenshot](image-file.png)

## 📊 Outcome
- Filter updated to show **current month** data as requested.  
- Potential risk of confusion remains because requirements are shifting.  
- No immediate way to challenge or clarify with end users.

## 🎯 Lessons Learned
- End users may change requirements unexpectedly, even contradicting earlier requests.  
- Capturing and documenting previous requirements is critical to avoid misunderstandings.  
- Translators play a key role in bridging communication gaps.  
- Flexibility is necessary, but it can feel frustrating when logic changes daily.

## 📌 Next Steps
- Continue documenting requirement changes for traceability.  
- Monitor if further corrections require reverting to previous month data again.  
- Consider proposing a dual-filter option (current + previous month) if the pattern continues.
