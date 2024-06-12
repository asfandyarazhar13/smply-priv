# Dataset Documentation

## Motivation

1. **For what purpose was the dataset created? Was there a specific task in mind? Was there a specific gap that needed to be filled? Please provide a description.**
   - The dataset was created for the purpose of privacy-preserving action recognition. The specific task in mind was to develop a method that could replace real humans in video data with 3D meshes to preserve privacy while maintaining the accuracy of action recognition models. The gap that needed to be filled was the lack of high-fidelity, privacy-preserving data augmentation frameworks that effectively bridge the realism gap associated with synthetic-based action recognition methods.

2. **Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)?**
   - The dataset was created by the authors of the paper, who are anonymized as "Anonymous Author(s)" for the NeurIPS 2024 submission.

3. **Who funded the creation of the dataset? If there is an associated grant, please provide the name of the grantor and the grant name and number.**
   - N/A.

4. **Any other comments?**
   - None.

## Composition

5. **What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? Are there multiple types of instances (e.g., movies, users, and ratings; people and interactions between them; nodes and edges)? Please provide a description.**
   - The instances in the dataset represent video sequences of human actions. Each instance is a video clip with human figures replaced by 3D meshes to ensure privacy.

6. **How many instances are there in total (of each type, if appropriate)?**
   - See sections 3.1 and 3.4 for details on the Kinetics and Downstream Datasets respectively. 

7. **Does the dataset contain all possible instances or is it a sample (not necessarily random) of instances from a larger set? If the dataset is a sample, then what is the larger set? Is the sample representative of the larger set (e.g., geographic coverage)? If so, please describe how this representativeness was validated/verified. If it is not representative of the larger set, please describe why not (e.g., to cover a more diverse range of instances, because instances were withheld or unavailable).**
   - See [`training/data`](/training/data) for the specific splits used for training. For the Kinetics dataset, we follow the splits used from the SynAPT paper and make our own splits using the proposed K-NEXUS algorithm (Section 3.1 in our paper). This was for dataset curation in regards to selecting a subset of classes and instances from the larger Kinetics-400 dataset.

8. **What data does each instance consist of? “Raw” data (e.g., unprocessed text or images) or features? In either case, please provide a description.**
   - Each instance consists of video data with human figures replaced by 3D meshes. The data includes both the raw video frames and the superimposed 3D mesh models.

9. **Is there a label or target associated with each instance? If so, please provide a description.**
   - Yes, each dataset has target classes. Associated labels can be found from each datasets documentation found online -- see the Usage subsection within the VideoMAE pre-training and Downstream Evaluation section in our GitHub's README. 

10. **Is any information missing from individual instances? If so, please provide a description, explaining why this information is missing (e.g., because it was unavailable). This does not include intentionally removed information, but might include, e.g., redacted text.**
    - N/A.

11. **Are relationships between individual instances made explicit (e.g., users' movie ratings, social network links)? If so, please describe how these relationships are made explicit.**
    - N/A.

12. **Are there recommended data splits (e.g., training, development/validation, testing)? If so, please provide a description of these splits, explaining the rationale behind them.**
    - N/A. 

13. **Are there any errors, sources of noise, or redundancies in the dataset? If so, please provide a description.**
    - Our M2M Kinetics dataset can tend to have minimal occlusions (see final section of our Appendix).

14. **Is the dataset self-contained, or does it link to or otherwise rely on external resources (e.g., websites, tweets, other datasets)? If it links to or relies on external resources, a) are there guarantees that they will exist, and remain constant, over time; b) are there official archival versions of the complete dataset (i.e., including the external resources as they existed at the time the dataset was created); c) are there any restrictions (e.g., licenses, fees) associated with any of the external resources that might apply to a future user? Please provide descriptions of all external resources and any restrictions associated with them, as well as links or other access points, as appropriate.**
    - See the Usage subsection within the VideoMAE pre-training and Downstream Evaluation section in our GitHub's README.  

15. **Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)? If so, please provide a description.**
    - N/A.

16. **Does the dataset contain data that, if viewed directly, might be offensive, insulting, threatening, or might otherwise cause anxiety? If so, please describe why.**
    - N/A.

17. **Does the dataset relate to people? If not, you may skip the remaining questions in this section.**
    - Yes.

18. **Does the dataset identify any subpopulations (e.g., by age, gender)? If so, please describe how these subpopulations are identified and provide a description of their respective distributions within the dataset.**
    - There is not any direct metadata on the individuals within the dataset based on any demographics. You can visually see said individuals, however after applying our M2M-augmentation on the Kinetics-150 dataset, these demographics are preserved. 

19. **Is it possible to identify individuals (i.e., one or more natural persons), either directly or indirectly (i.e., in combination with other data) from the dataset? If so, please describe how.**
    - See question 18.

20. **Does the dataset contain data that might be considered sensitive in any way (e.g., data that reveals racial or ethnic origins, sexual orientations, religious beliefs, political opinions or union memberships, or locations; financial or health data; biometric or genetic data; forms of government identification, such as social security numbers; criminal history)? If so, please provide a description.**
    - N/A.

21. **Any other comments?**
    - None.

## Collection Process

22. **How was the data associated with each instance acquired? Was the data directly observable (e.g., raw text, movie ratings), reported by subjects (e.g., survey responses), or indirectly inferred/derived from other data (e.g., part-of-speech tags, model-based guesses for age or language)? If data was reported by subjects or indirectly inferred/derived from other data, was the data validated/verified? If so, please describe how.**
    - Publicly available video datasets.

23. **What mechanisms or procedures were used to collect the data (e.g., hardware apparatus or sensor, manual human curation, software program, software API)? How were these mechanisms or procedures validated?**
    - N/A.

24. **If the dataset is a sample from a larger set, what was the sampling strategy (e.g., deterministic, probabilistic with specific sampling probabilities)?**
    - Strategic sampling using our propsed K-NEXUS algorithm and SynAPT splits (from their paper, see our Appendix's training details for reference).

25. **Who was involved in the data collection process (e.g., students, crowdworkers, contractors) and how were they compensated (e.g., how much were crowdworkers paid)?**
    - N/A.

26. **Over what timeframe was the data collected? Does this timeframe match the creation timeframe of the data associated with the instances (e.g., recent crawl of old news articles)? If not, please describe the timeframe in which the data associated with the instances was created.**
    - N/A.

27. **Were any ethical review processes conducted (e.g., by an institutional review board)? If so, please provide a description of these review processes, including the outcomes, as well as a link or other access point to any supporting documentation.**
    - N/A.

28. **Does the dataset relate to people? If not, you may skip the remaining questions in this section.**
    - Yes.

29. **Did you collect the data from the individuals in question directly, or obtain it via third parties or other sources (e.g., websites)?**
    - Datasets are publically availabe. See the Usage subsection within the VideoMAE pre-training and Downstream Evaluation section in our GitHub's README. 

30. **Were the individuals in question notified about the data collection? If so, please describe (or show with screenshots or other information) how notice was provided, and provide a link or other access point to, or otherwise reproduce, the exact language of the notification itself.**
    - N/A.

31. **Did the individuals in question consent to the collection and use of their data? If so, please describe (or show with screenshots or other information) how consent was requested and provided, and provide a link or other access point to, or otherwise reproduce, the exact language to which the individuals consented.**
    - We obtained videos from pre-curated publicly available datasets.

32. **If consent was obtained, were the consenting individuals provided with a mechanism to revoke their consent in the future or for certain uses? If so, please provide a description, as well as a link or other access point to the mechanism (if appropriate).**
    - N/A.

33. **Has an analysis of the potential impact of the dataset and its use on data subjects (e.g., a data protection impact analysis) been conducted? If so, please provide a description of this analysis, including the outcomes, as well as a link or other access point to any supporting documentation.**
    - N/A.

34. **Any other comments?**
    - None.

## Preprocessing/Cleaning/Labeling

35. **Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remainder of the questions in this section.**
    - Yes, preprocessing was done including masking, inpainting, and body mesh recovery. The framework involves detecting and removing human figures from the video frames, followed by inpainting to fill the regions with plausible background content. Finally, detailed 3D mesh models of the human figures are superimposed onto the inpainted video frames.

36. **Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? If so, please provide a link or other access point to the “raw” data.**
    - Each instance is an augmented video of a human mesh performing an action.

37. **Is the software used to preprocess/clean/label the instances available? If so, please provide a link or other access point.**
    - N/A.

38. **Any other comments?**
    - None.

## Uses

39. **Has the dataset been used for any tasks already? If so, please provide a description.**
    - We see that M2M-Kinetics is a concrete method to be used for privacy preservation of datasets by removing humans and replacing them with mesh figures. 

40. **Is there a repository that links to any or all papers or systems that use the dataset? If so, please provide a link or other access point.**
    - N/A.

41. **What (other) tasks could the dataset be used for?**
    - The dataset could be used for any tasks involving action recognition, particularly those requiring privacy-preserving techniques.

42. **Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a future user might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other undesirable harms (e.g., financial harms, legal risks)? If so, please provide a description. Is there anything a future user could do to mitigate these undesirable harms?**
    - The main use of SMPLy Private and M2M-augmentation is to overcome some of the ethics and privacy issues of real video datasets. Currently, we do not see these concerns influencing future uses in any way. 

43. **Are there tasks for which the dataset should not be used? If so, please provide a description.**
    - Refer to the original usage agreements of all datasets. 

44. **Any other comments?**
    - None.

## Distribution

45. **Will the dataset be distributed to third parties outside of the entity (e.g., company, institution, organization) on behalf of which the dataset was created? If so, please provide a description.**
    - Yes, instructions on how to replicate the M2m-augmentations for SMPLy Private is available.

46. **How will the dataset be distributed (e.g., tarball on website, API, GitHub)? Does the dataset have a digital object identifier (DOI)?**
    - Documentation available on GitHub.

47. **When will the dataset be distributed?**
    - N/A.

48. **Will the dataset be distributed under a copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)? If so, please describe this license and/or ToU, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms or ToU, as well as any fees associated with these restrictions.**
    - Agreement on the SMPL-X and Kinetics licenses must be followed.

49. **Have any third parties imposed IP-based or other restrictions on the data associated with the instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms, as well as any fees associated with these restrictions.**
    - Users may need to create an account for access to datasets at the external links provided on GitHub. 

50. **Do any export controls or other regulatory restrictions apply to the dataset or to individual instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any supporting documentation.**
    - No.

51. **Any other comments?**
    - None.

## Maintenance

52. **Who will be supporting/hosting/maintaining the dataset?**
    - The original authors. 

53. **How can the owner/curator/manager of the dataset be contacted (e.g., email address)?**
    - Create an issue request at the GitHub repo if needed. 

54. **Is there an erratum? If so, please provide a link or other access point.**
    - No.

55. **Will the dataset be updated (e.g., to correct labeling errors, add new instances, delete instances)? If so, please describe how often, by whom, and how updates will be communicated to users (e.g., mailing list, GitHub)?**
    - To be posted on GitHub. 

56. **If the dataset relates to people, are there applicable limits on the retention of the data associated with the instances (e.g., were individuals in question told that their data would be retained for a fixed period of time and then deleted)? If so, please describe these limits and explain how they will be enforced.**
    - N/A.

57. **Will older versions of the dataset continue to be supported/hosted/maintained? If so, please describe how. If not, please describe how its obsolescence will be communicated to users.**
    - Former versions would still be available on the GitHub.

58. **If others want to extend/augment/build on/contribute to the dataset, is there a mechanism for them to do so? If so, please provide a description. Will these contributions be validated/verified? If so, please describe how. If not, why not? Is there a process for communicating/distributing these contributions to other users? If so, please provide a description.**
    - Others may do this but should first contact the original authors about any relevant extensions and/or fixes.

59. **Any other comments?**
    - None.
