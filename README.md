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
| AJA  | ![AJA](https://raw.githubusercontent.com/TFC-Gael/Logo/main/AJA.png) |
| ASM  | ![ASM](https://raw.githubusercontent.com/TFC-Gael/Logo/main/ASM.png) |
| ASSE | ![ASSE](https://raw.githubusercontent.com/TFC-Gael/Logo/main/ASSE.png) |
| FCM  | ![FCM](https://raw.githubusercontent.com/TFC-Gael/Logo/main/FCM.png) |
| FCN  | ![FCN](https://raw.githubusercontent.com/TFC-Gael/Logo/main/FCN.png) |
| L1   | ![L1](https://raw.githubusercontent.com/TFC-Gael/Logo/main/L1.png) |
| LOSC | ![LOSC](https://raw.githubusercontent.com/TFC-Gael/Logo/main/LOSC.png) |
| MHSC | ![MHSC](https://raw.githubusercontent.com/TFC-Gael/Logo/main/MHSC.png) |
| MHSC50 | ![MHSC50](https://raw.githubusercontent.com/TFC-Gael/Logo/main/MHSC50.png) |
| OGCN | ![OGCN](https://raw.githubusercontent.com/TFC-Gael/Logo/main/OGCN.png) |
| OL   | ![OL](https://raw.githubusercontent.com/TFC-Gael/Logo/main/OL.png) |
| OM   | ![OM](https://raw.githubusercontent.com/TFC-Gael/Logo/main/OM.png) |
| PSG  | ![PSG](https://raw.githubusercontent.com/TFC-Gael/Logo/main/PSG.png) |
| RCL  | ![RCL](https://raw.githubusercontent.com/TFC-Gael/Logo/main/RCL.png) |
| RCS  | ![RCS](https://raw.githubusercontent.com/TFC-Gael/Logo/main/RCS.png) |
| SB29 | ![SB29](https://raw.githubusercontent.com/TFC-Gael/Logo/main/SB29.png) |
| SCO  | ![SCO](https://raw.githubusercontent.com/TFC-Gael/Logo/main/SCO.png) |
| SDR  | ![SDR](https://raw.githubusercontent.com/TFC-Gael/Logo/main/SDR.png) |
| SDR2 | ![SDR2](https://raw.githubusercontent.com/TFC-Gael/Logo/main/SDR2.png) |
| SRFC | ![SRFC](https://raw.githubusercontent.com/TFC-Gael/Logo/main/SRFC.png) |
| TFC  | ![TFC](https://raw.githubusercontent.com/TFC-Gael/Logo/main/TFC.png) |

This README will help users generate and display logos dynamically in a table using R and also download them easily.

