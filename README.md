# Maria-Guzeva
# Smart Waste Sorting Assistant

## Summary
This project aims to develop an AI-powered assistant that helps users correctly sort their waste into different categories (e.g., plastic, paper, organic, glass, general waste). By using image recognition, the system will identify waste items and provide instant sorting recommendations.

## Background
Mis-sorting waste is a common problem globally, leading to inefficiencies in recycling processes, contamination of recyclable materials, and increased landfill waste. This issue contributes to environmental degradation and resource depletion. Personally, I've often found myself unsure about where to dispose of certain items, especially packaging with multiple materials or obscure labels. This project is important because improving waste sorting at the individual level can significantly boost recycling rates and promote a circular economy.

* Problem 1: Low recycling rates due to improper sorting.
* Problem 2: Contamination of recyclable waste streams.
* Problem 3: Lack of knowledge among consumers about correct waste disposal.

## How is it used?
The solution would be a mobile application or a web-based tool. A user would simply take a picture of a waste item using their smartphone camera. The application would then process the image using a trained AI model and display the recommended waste category (e.g., "Plastic," "Compost," "Landfill").

This solution is needed in various environments:
* **At home:** For daily household waste sorting.
* **In public spaces:** For visitors unsure about local recycling rules.
* **In offices or schools:** To educate and assist employees/students in proper waste disposal.

The primary users would be individuals who want to sort their waste correctly but lack the knowledge or time to research each item. The app needs to be user-friendly, fast, and provide clear, unambiguous recommendations. It should also account for varying local recycling guidelines.
import pandas as pd
import pandas as pd

def classify_plastic_item(item_name):
    """
    Simulates a basic plastic waste classification based on common item types.
    This is a highly simplified example, not an actual AI model.
    The recyclability status is based on general knowledge, which varies by region.
    """

    # Data inspired by common plastic items discussed in "Our Plastic Earth" context
    # In a real application, this would be a large, trained dataset.
    plastic_items_data = {
        "PET bottle": {"type": "Plastic #1 (PET)", "recyclable": True, "notes": "Widely recyclable, often found in water bottles, soda bottles."},
        "HDPE milk jug": {"type": "Plastic #2 (HDPE)", "recyclable": True, "notes": "Widely recyclable, commonly used for milk jugs, detergent bottles."},
        "plastic bag": {"type": "Plastic #4 (LDPE)", "recyclable": False, "notes": "Often not accepted in curbside recycling; requires special drop-off."},
        "yogurt container": {"type": "Plastic #5 (PP)", "recyclable": True, "notes": "Becoming more widely recyclable, check local guidelines."},
        "styrofoam cup": {"type": "Plastic #6 (PS)", "recyclable": False, "notes": "Rarely recyclable curbside; often sent to landfill."},
        "plastic cutlery": {"type": "Plastic #6 (PS)", "recyclable": False, "notes": "Small and often made of unrecyclable plastic; typically landfill."},
        "food wrapper": {"type": "Mixed Plastics/Multi-layer", "recyclable": False, "notes": "Often difficult to recycle due to mixed materials."},
        "PVC pipe": {"type": "Plastic #3 (PVC)", "recyclable": False, "notes": "Not typically accepted in curbside recycling."},
        "clamshell container": {"type": "Mixed Plastics/PET/PS", "recyclable": False, "notes": "Often problematic due to mixed materials or different plastic types."},
        "plastic film": {"type": "Mixed Plastics/LDPE", "recyclable": False, "notes": "Similar to plastic bags, usually requires special drop-off."},
        "shampoo bottle": {"type": "Plastic #2 (HDPE)", "recyclable": True, "notes": "Check for pumps/lids, usually recyclable after rinsing."},
        "straw": {"type": "Plastic #5 (PP) or #6 (PS)", "recyclable": False, "notes": "Too small to be sorted, typically landfill."},
        "disposable coffee cup lid": {"type": "Plastic #6 (PS)", "recyclable": False, "notes": "Often made of unrecyclable plastic, usually landfill."},
    }

    item_name_lower = item_name.lower()

    if item_name_lower in plastic_items_data:
        data = plastic_items_data[item_name_lower]
        print(f"\n--- Item Classification: {item_name.title()} ---")
        print(f"Plastic Type: {data['type']}")
        print(f"Recyclable: {'Yes' if data['recyclable'] else 'No'}")
        print(f"Notes: {data['notes']}")
        if not data['recyclable']:
            print("Action: Consider alternatives or proper disposal methods.")
    else:
        print(f"\n--- Item Classification: {item_name.title()} ---")
        print("Information not found for this specific plastic item.")
        print("Please check local recycling guidelines or consider if it's general waste.")

def main():
    print("Welcome to the Plastic Waste Classifier (Simplified)! 👋")
    print("This tool provides basic information on common plastic items and their recyclability.")
    print("Remember: Local recycling rules vary!")

    while True:
        item = input("\nEnter a plastic item (e.g., 'PET bottle', 'plastic bag', 'yogurt container', 'styrofoam cup', 'food wrapper', 'straw'): ").strip()
        if not item:
            print("Please enter an item name.")
            continue
        if item.lower() == 'quit':
            print("Exiting the classifier. Thank you for thinking about sustainability!")
            break

        classify_plastic_item(item)

if __name__ == "__main__":
    main()
