# Mushroom-examples

![image](https://user-images.githubusercontent.com/24855529/170824801-560c966c-eccb-4e17-b4f3-2d5891aad5f3.png)

Please see the example of this image in the file "Mushroom_Area_card.yaml"

Create a Card where we can use several mushrooms - custom:vertical-stack-in-card
on first line will have a custom:mushroom-template-card with "primary" as Title and "secondary" for extra data


    secondary: >-
      {{ states('sensor.ewelink_th01_1debcd24_temperature') }}°C | 
      {{ states('sensor.ewelink_th01_1debcd24_humidity') }} % | 
      {{ states('sensor.ewelink_th01_1debcd24_power')}} %  

there is a way  to add enter between lines:

![image](https://user-images.githubusercontent.com/24855529/170824986-dea18b67-ec3a-497f-910e-ef14517b2439.png)

    secondary: >-
      {{ states('sensor.ewelink_th01_1debcd24_temperature') }}°C 

      {{ states('sensor.ewelink_th01_1debcd24_humidity') }} %  

      {{ states('sensor.ewelink_th01_1debcd24_power')}} %  


For the second line with several buttons we need to create a custom:vertical-stack-in-card and horizontal: true to have the buttons organized in horizontal wah then you can create several custom:mushroom-template-card for each button.

![image](https://user-images.githubusercontent.com/24855529/170825035-96c6da60-b88d-4e44-b729-78217afe6fe0.png)

 type: custom:vertical-stack-in-card
    horizontal: true
    cards:
      - type: custom:mushroom-template-card      

Code that allow you to change icon depending on the state
        icon: |-
          {% if is_state('switch.hall_lights_channel_2', 'on') %}
            mdi:outdoor-lamp
          {% else %}
            mdi:outdoor-lamp
          {% endif %}
          
Code that allow you to change icon colour depending on the state
        icon_color: |-
          {% if is_state('switch.hall_lights_channel_2', 'on') %}
            yellow
          {% endif %}
        theme: ios-dark-mode-dark-green

if you want to create ghost buttons  to create spaces, inside the vertical-stack-in-card, create a mushroom-template-card without entity like the following example:
![Screen Shot 2022-06-15 at 19 26 22](https://user-images.githubusercontent.com/24855529/173898701-d856f948-f703-4b62-b1d5-d15b68258969.png)

  - type: custom:vertical-stack-in-card
    horizontal: true
    cards:
      - type: custom:mushroom-template-card
        entity: false
        layout: vertical
        icon: false
        icon_color: false




For the person card (in progress). The color of the icons are not changing according withe the status. check the file "Mushroom_Person_Example.yaml"

![Screen Shot 2022-06-15 at 19 14 19](https://user-images.githubusercontent.com/24855529/173897151-f9af62e3-b7e0-453f-ac53-890314512620.png)


