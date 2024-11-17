𝗗𝗲𝘀𝗶𝗴𝗻𝗶𝗻𝗴 𝗮 𝗙𝗹𝗲𝘅𝗶𝗯𝗹𝗲 𝗮𝗻𝗱 𝗖𝗼𝗻𝗳𝗶𝗴𝘂𝗿𝗮𝗯𝗹𝗲 𝗖𝗔𝗣𝗧𝗖𝗛𝗔 𝗦𝘆𝘀𝘁𝗲𝗺

This project implements a CAPTCHA generation and validation system designed to enhance security for user interactions. The system is built using Mendix and Java and includes the following key functionalities:

Here’s how it works:

    Service-Level Configuration: Each service defines key security policies, such as:
    🔑 Maximum unverified attempts per session.
    ⏳ Block duration for users after failed attempts.
    🕒 Expiration time for each CAPTCHA.

    Custom CAPTCHA Configurations: Services are linked to specific CAPTCHA configurations, which define:
    🔢 Whether the CAPTCHA uses letters, numbers, or both.
    🧩 The complexity level of the CAPTCHA design.

    Complexity Levels: Each level customizes the generated CAPTCHA image, including:
    🎨 Background colors.
    🖋️ Font sizes and colors.
    ✏️ Noise elements, such as ellipses, dots, and lines, with configurable counts and colors.



Features

    1- Dynamic CAPTCHA Image Generation:
        Generates CAPTCHA images with customizable complexity.
        Supports various visual effects:
            Wavy text distortion.
            Noise lines, ellipses, and dots for added complexity.
        Configurable background and text colors.
        Anti-aliasing for smoother text rendering.

    2- Base64 Encoding for Image Transmission:
        CAPTCHA images are encoded in Base64 format for secure transmission via APIs.

    3- CAPTCHA Storage and Validation:
        CAPTCHA data is stored in the internal database.
        A unique session identifier is used to associate CAPTCHA with users.
        Validation ensures user-entered text matches the stored CAPTCHA.

    

    4- Security Measures:
        CAPTCHA values are hashed before storage.
        Validation uses Mendix’s MendixHashString library for secure string comparison.
        Configurable maximum attempts before CAPTCHA expiration or refresh.


   Java Action: (verifyCaptcha)
   
Purpose

This Java action validates the user-entered CAPTCHA string against the hashed value stored in the database.
Key Logic

    #Retrieve the stored CAPTCHA object using the session identifier and transaction ID.
    #Use the MendixHashString.verifyValue method to securely compare the stored hash with the user input.
    #Return true if the validation succeeds, false otherwise.     
