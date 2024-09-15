# -*- coding: utf-8 -*-
"""
Created on Sun Sep 15 16:05:00 2024

@author: Manvitha
"""
from langchain import OpenAI
import openai
import os

# Initialize OpenAI client
openai.api_key = os.getenv('OPENAI_API_KEY')
def generate_image(prompt):
    try:
        # Use the updated API method for image generation
        response = openai.Image.create(
            prompt=prompt,
            n=1,
            size="1024x1024"  # Choose the appropriate size
        )
        # Adjust according to the response structure
        image_url = response['data'][0]['url']
    except KeyError as e:
        print(f"KeyError: {e}")
        print("Response:", response)
        image_url = 'Error retrieving image URL'
    return image_url

def main():
    description = input("Enter a description for the image: ")
    image_url = generate_image(description)
    print(f"Generated Image URL: {image_url}")
if __name__ == "__main__":
    main()
