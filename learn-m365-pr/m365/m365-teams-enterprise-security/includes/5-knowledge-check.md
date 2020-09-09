  - content: "When considering the data configuration level for your app protection policy, which level introduces the data leakage prevention mechanism for the first time?"
    choices:
    - content: Enterprise basic data protection.
      isCorrect: false
      explanation: "That's incorrect. This is level 1 of the data protection framework and does not include data leakage prevention mechanisms."
    - content: Enterprise enhanced data protection.
      isCorrect: true
      explanation: "That's correct.This is level 2 of the data protection framework, and it introduces the data leakage prevention mechanism as well as minimum OS requirements."
    - content: Enterprise high data protection.
      isCorrect: false
      explanation: "That's incorrect. This is level 3 of the data protection framework and which incorporates all the elements of Levels 1 and 2."

  - content: "When considering the data configuration level for your app protection policy, which level introduces the data leakage prevention mechanism for the first time?"
    choices:
    - content: Enterprise basic data protection.
      isCorrect: false
      explanation: "That's incorrect. This is level 1 of the data protection framework and does not include data leakage prevention mechanisms."
    - content: Enterprise enhanced data protection.
      isCorrect: true
      explanation: "That's correct.This is level 2 of the data protection framework, and it introduces the data leakage prevention mechanism as well as minimum OS requirements."
    - content: Enterprise high data protection.
      isCorrect: false
      explanation: "That's incorrect. This is level 3 of the data protection framework and which incorporates all the elements of Levels 1 and 2."

  - content: "What is best practice concerning the Continue Anyway message on the blocking page?"
    choices:
    - content: Configuring the Continue Anyway message is not recommended.
      isCorrect: true
      explanation: "That's correct. If Safe Links measures the reputation of a site and finds it lacking, best practice recommends that you do not configure the Continue Anyway message to allow further click-through."
    - content: Configuring the Continue Anyway message is recommended.
      isCorrect: false
      explanation: "That's incorrect. If Safe Links measures the reputation of a site and finds it lacking, best practice recommends that you do not configure the Continue Anyway message to allow further click-through."
    - content: Configuring the Continue Anyway message depends on your organization's policy.
      isCorrect: false
      explanation: "That's incorrect. If Safe Links measures the reputation of a site and finds it lacking, best practice recommends that you do not configure the Continue Anyway message to allow further click-through."

  - content: "What is an emergency access account?"
    choices:
    - content: The account used when someone forgets their password.
      isCorrect: false
      explanation: "That's incorrect. The emergency account is not used when someone forgets their password."
    - content: The account used to sign in when you can't sign in or activate another user's account as administrator.
      isCorrect: true
      explanation: "That's correct. Emergency access or break-glass accounts prevent tenant-wide account lockout in the unlikely event all administrators get locked with out MFA."
    - content: The accounts used to sign in with multi-factor authentication.
      isCorrect: false
      explanation: "That's incorrect. Multi-factor authentication is an additional sign in step. You do not use emergency access accounts as part of MFA sign in."

  - content: "How can you test multi-factor authentication for Teams?"
    choices:
    - content: Conditional access in Azure.
      isCorrect: false
      explanation: "That's incorrect. You can configure Conditional Access in Azure but not test it."
    - content: Conditional Access What If tool.
      isCorrect: true
      explanation: "That's correct. The Conditional Access What If tool allows you to test MFA for different criteria."
    - content: Conditional Access Users and Groups.
      isCorrect: false
      explanation: "That's incorrect. Users and Groups is part of the Conditional Access policy, but not a way of testing whether MFA works correctly."
