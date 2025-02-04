# Displaying Logos in a Table

This repository contains various logos in PNG format. The following R code uses the `gt` package to display all PNG images from this repository in a formatted table.

## R Code to Display Logos

```r
# Load necessary libraries
library(gt)
library(dplyr)
library(glue)

# Define the repository base URL
repo_url <- "https://raw.githubusercontent.com/TFC-Gael/Logo/main/"

# List of logo file names
logos <- c("AJA.png", "ASM.png", "ASSE.png", "FCM.png", "FCN.png", "L1.png", "LOSC.png", "MHSC.png", "MHSC50.png", "OGCN.png", "OL.png", "OM.png", "PSG.png", "RCL.png", "RCS.png", "SB29.png", "SCO.png", "SDR.png", "SDR2.png", "SRFC.png", "TFC.png")

# Create a data frame with image URLs
data <- data.frame(
  Name = gsub(".png", "", logos),
  Logo = glue("<img src='{repo_url}{logos}' height='100'>")
)

# Generate the table
data %>%
  gt() %>%
  fmt_markdown(columns = "Logo")
```

## R Code to Download All Logos

```r
# Define the repository base URL
repo_url <- "https://raw.githubusercontent.com/TFC-Gael/Logo/main/"

# List of logo file names
logos <- c("AJA.png", "ASM.png", "ASSE.png", "FCM.png", "FCN.png", "L1.png", "LOSC.png", "MHSC.png", "MHSC50.png", "OGCN.png", "OL.png", "OM.png", "PSG.png", "RCL.png", "RCS.png", "SB29.png", "SCO.png", "SDR.png", "SDR2.png", "SRFC.png", "TFC.png")

# Download each file
for (logo in logos) {
  download.file(url = paste0(repo_url, logo), destfile = logo, mode = "wb")
}
```

## How It Works
- The script defines the base URL where the logos are stored.
- A list of PNG file names is created (you can extend this dynamically by reading the repository contents).
- A data frame is built where the `Logo` column contains image links.
- The `gt` package is used to format and display the table in an HTML-friendly manner.
- An additional script is included to download all the logos automatically.

### Example Output
| Name | Logo |
|------|------|
| AJA  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/AJA.png' height='80'> |
| ASM  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/ASM.png' height='80'> |
| ASSE | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/ASSE.png' height='80'> |
| FCM  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/FCM.png' height='80'> |
| FCN  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/FCN.png' height='80'> |
| L1   | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/L1.png' height='80'> |
| LOSC | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/LOSC.png' height='80'> |
| MHSC | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/MHSC.png' height='80'> |
| MHSC50 | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/MHSC50.png' height='80'> |
| OGCN | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/OGCN.png' height='80'> |
| OL   | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/OL.png' height='80'> |
| OM   | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/OM.png' height='80'> |
| PSG  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/PSG.png' height='80'> |
| RCL  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/RCL.png' height='80'> |
| RCS  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/RCS.png' height='80'> |
| SB29 | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/SB29.png' height='80'> |
| SCO  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/SCO.png' height='80'> |
| SDR  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/SDR.png' height='80'> |
| SDR2 | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/SDR2.png' height='80'> |
| SRFC | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/SRFC.png' height='80'> |
| TFC  | <img src='https://raw.githubusercontent.com/TFC-Gael/Logo/main/TFC.png' height='80'> |

This README will help users generate and display logos dynamically in a table using R and also download them easily.

