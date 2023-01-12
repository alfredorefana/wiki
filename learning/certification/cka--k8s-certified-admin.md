# Certified Kubernetes Administrator (CKA)

In this page, I'll try to give answers to question "How to nail the Certified Kubernetes Administrator (CKA) exam on the first attempt?" by sharing some experiences from my own CKA journey. If you’re targeting the same destination, hopefully, it can add some help!


## Why CKA?

The purpose of the Certified Kubernetes Administrator (CKA) program is to provide assurance that CKAs have the skills, knowledge, and competency to perform the responsibilities of Kubernetes administrators. 
So, in short, this certificate demonstrates your competency,  establishes your credibility and value in the job market, and hopefully makes you stand out in front of employer.  

You can read details on the exam [here from Cloud Native Foundation (CNF)](https://www.cncf.io/certification/cka/) and [here from Linux Foundation (LF)](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/).

The CKA is hard but a rewarding certification. The amazing thing about it is that it's hands-on and practical, which means no memorization or multiple-choice questions.
I never liked theoretical questions and too many worded stuff. 


## Highlights about this exam in case you don’t know it yet

- Online-proctored exam, performance-based (NOT multi-choice-question), you need to solve 17-20 challenges on an RDP environment (via PSI secure browser) by Kubernetes commands

- Duration of Exam: 2 hours
- Certification validity: 3 Years
- Passing score: 66/100
- Exam fee: 395$ (as of Jan.2023). Discount coupons are available sometimes, on Black Friday or Cyber Monday for example)
- You can access and use the official K8s documentation 


## My Comprehensive List of Study Resources

### Prerequisites 

There is no prior knowledge required, but if you are good at containerization, Docker and Linux, it would help a lot.

### How to study?

I used the following materials and platforms to prepare for the CKA exam:

- [Introduction to Containers and Docker](https://acloudguru.com/course/introduction-to-containers-and-docker)
- [Introduction to Kubernetes](https://acloudguru.com/course/introduction-to-kubernetes)
- [Kubernetes for the Absolute Beginners - Hands-on](https://www.udemy.com/course/learn-kubernetes/)
- [Introduction to OpenShift](https://learn.acloud.guru/course/introduction-to-openshift/overview)
- [Certified Kubernetes Administrator (CKA)](https://acloudguru.com/course/certified-kubernetes-administrator-cka)

    - Good course
    - Well organized in term of presentation and explanation with visualization
    - They offer free playground for Azure/GCP/AWS platform, and you don't need to think of where to build your cluster for practices
    - Free pre-configured K8s cluster for labs
    - Unfortunately, the course's contents are not up-to-date to the CKA curricilum 
    - Labs are poor and too easy, especially mock exams, so don't just rely on them for clearing the exam

- [Kubernetes Fundamentals (LFS258) from Linux Foundation](https://training.linuxfoundation.org/training/kubernetes-fundamentals/)

    - Very Up-to-date with the [CKA cirrucilum](https://github.com/cncf/curriculum)
    - Theory well explained and structured
    - Contents are for your pace reading
    - Practice exercises and labs are very well prepared and explained in detail for your understading
    - This course can be purchased in bundle with the exam

- [Certified Kubernetes Administrator labs](https://kodekloud.com/courses/labs-certified-kubernetes-administrator-with-practice-tests/)

    - Very good lab/test cases
    - They have some lightning lab and mock exams, which you should repeat a few times to get familiar with K8s stuff and improve the speed
    - Lab’s difficulty level is close to the real exam

- [CKS/CKA/CKAD Simulator -- killer.sh](https://killer.sh/cka)

    - 2 free runs with exam purchased from LF
    - Do at least ONCE (timed) then REVIEW
    - The explanations of answer are very well done, try to read and understand them all
    - Questions and scenarios are harder than the real exam
    - Your environment is open for the following 36hrs after activation, so you can go back and reflect/check, etc


## Advices

- Give yourself time for learning and practicing

- Time is your most valuable resource, and speed is your best friend
- First be imperative, then declarative. Practice this in handling K8s objects
- Use shortname of object if it has one
- Understand k8s official documentation as you'll have access to it during the exam
- Read and always check up-to-date exam curriculum (aka exam blue print)
- I would recommend to do the exam on at least 15" monitor or laptop
- Practice -- Practice -- Practice and again practice


## Other relevant links

- [Important Instructions: CKA and CKAD, aka (official) Exam Tips](https://docs.linuxfoundation.org/tc-docs/certification/tips-cka-and-ckad)

- [kubernetes api 1-page reference v1.26.0](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.26/)
- [kubectl Commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands) with explanation and example. Basically, it is a webpage version of the `kubectl --help` 
- [kubectl](https://kubernetes.io/docs/reference/kubectl/kubectl/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [CKS/CKA/CKAD Simulator -- killer.sh](https://killer.sh/)
- [A very nice video advice from jedi.ascode()](https://youtu.be/8VK9NJ3pObU)
- [Frequently Asked Questions: CKA and CKAD & CKS](https://docs.linuxfoundation.org/tc-docs/certification/faq-cka-ckad-cks)

