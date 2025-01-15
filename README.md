# Image Caption Generator

This repository contains a Python script that downloads images from a specified webpage, generates captions for these images using a pre-trained BLIP (Bootstrapped Language-Image Pre-training) model, and saves the captions alongside the corresponding image URLs to a text file.

## Features

- Scrapes images from a given webpage using `BeautifulSoup`.
- Filters out unwanted images (e.g., SVGs, very small images).
- Generates descriptive captions for each image using the Salesforce BLIP model.
- Saves the image URLs and captions to a file for easy reference.

## Requirements

To run this script, you need the following Python libraries installed:

- `requests`
- `Pillow`
- `beautifulsoup4`
- `transformers`

Install them using pip:

```bash
pip install requests pillow beautifulsoup4 transformers
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/your-username/image-caption-generator.git
cd image-caption-generator
```

2. Update the URL in the script to the webpage you want to scrape:

```python
url = "https://sv.wikipedia.org/wiki/Stockholm"
```

3. Run the script:

```bash
python image_caption_generator.py
```

4. The script will save the image URLs and their captions to `captions.txt` in the same directory.

## How It Works

1. **Web Scraping**: The script uses `BeautifulSoup` to scrape all image elements (`<img>` tags) from the specified webpage.
2. **Image Filtering**: Images that are too small or in SVG format are skipped.
3. **Image Captioning**:
   - Images are downloaded and converted to RGB format using the `Pillow` library.
   - The BLIP model from the `transformers` library processes each image to generate a caption.
4. **Output**: Captions are saved to a file (`captions.txt`) with their corresponding image URLs.

## Example Output

A sample entry in `captions.txt` might look like this:

```
https://upload.wikimedia.org/wikipedia/commons/1/15/IBM_logo.svg: IBM logo on a white background
```

## Limitations

- The script may not handle all edge cases, such as non-standard webpage structures or inaccessible image URLs.
- Large webpages with many images may take significant time to process.
- Requires an internet connection for both webpage scraping and model usage.

## Acknowledgments

- The [Salesforce BLIP model](https://huggingface.co/Salesforce/blip-image-captioning-base) for image captioning.
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) for web scraping.
- [Pillow](https://python-pillow.org/) for image processing.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

