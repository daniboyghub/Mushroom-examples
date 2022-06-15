# Mushroom-examples

![image](https://user-images.githubusercontent.com/24855529/170824801-560c966c-eccb-4e17-b4f3-2d5891aad5f3.png)

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


For the person card (in progress). The color of the icons are not changing according withe the status. check the file "Mushroom_Person_Example.yaml"
![Screen Shot 2022-06-15 at 19 14 19](https://user-images.githubusercontent.com/24855529/173897151-f9af62e3-b7e0-453f-ac53-890314512620.png)


