# MAUI Profile UI - Assignment Requirements Documentation

## 📱 Project Overview
This MAUI application implements an Instagram-style profile UI with a custom lavender/purple theme, matching the exact specifications provided by your lecturer.

---

## ✅ QUESTION A: Rounded Profile Picture with Color Border [2 marks]

### 📍 Location
**File:** `MainPage.xaml`  
**Lines:** 18-30

### 🎯 Requirements Met
- ✅ Circular/rounded profile picture
- ✅ Colored border (purple: `#9C27B0`)
- ✅ Border thickness of 3 pixels
- ✅ Proper aspect ratio maintained

### 💻 Implementation Code
```xml
<!-- ========================================================================== -->
<!-- QUESTION A: Rounded profile picture with color border [2 marks]          -->
<!-- ========================================================================== -->
<!-- Profile Picture with Circular Purple Border -->
<Border Grid.Column="0"
        StrokeThickness="3"
        Stroke="#9C27B0"
        StrokeShape="RoundRectangle 50"
        WidthRequest="90"
        HeightRequest="90"
        VerticalOptions="Start">
    <Image Source="owner1.jpeg" 
           Aspect="AspectFill"/>
</Border>
<!-- ========================================================================== -->
<!-- END OF QUESTION A                                                         -->
<!-- ========================================================================== -->
```

### 🔑 Key Technical Details
- **Control Used:** `Border` with nested `Image`
- **Shape:** `StrokeShape="RoundRectangle 50"` creates the circular effect
- **Border Color:** `Stroke="#9C27B0"` (purple, matching BTS theme)
- **Border Width:** `StrokeThickness="3"`
- **Image Sizing:** `WidthRequest="90"` and `HeightRequest="90"` for perfect circle
- **Image Fit:** `Aspect="AspectFill"` ensures image fills the circle without distortion

---

## ✅ QUESTION B: Expandable Labels with Tail Truncation [3 marks]

### 📍 Location
**File:** `MainPage.xaml`  
**Lines:** 109-139

### 🎯 Requirements Met
- ✅ Uses **MAUI Community Toolkit Expander** (as hinted)
- ✅ Text truncation with ellipsis ("...")
- ✅ "Read More" link visible
- ✅ Expandable to show full content
- ✅ Tail truncation mode implemented

### 💻 Implementation Code
```xml
<!-- ========================================================================== -->
<!-- QUESTION B: Expandable labels with tail truncation [3 marks]             -->
<!-- Using MAUI Community Toolkit Expander                                     -->
<!-- ========================================================================== -->
<toolkit:Expander x:Name="BioExpander">
    <toolkit:Expander.Header>
        <Grid ColumnDefinitions="*,Auto">
            <Label Grid.Column="0"
                   Text="Jeon Jung-kook (Korean: 전정국; born September 1, 1997), known mononymously as Jungkook, is a South Korean singer"
                   LineBreakMode="TailTruncation"
                   MaxLines="2"
                   FontSize="14"
                   TextColor="#333"/>
            <Label Grid.Column="1" 
                   Text="Read More"
                   FontSize="14"
                   TextColor="#9C27B0"
                   FontAttributes="Bold"
                   Margin="5,0,0,0"/>
        </Grid>
    </toolkit:Expander.Header>
    <toolkit:Expander.Content>
        <Label Text="Jeon Jung-kook (Korean: 전정국; born September 1, 1997), known mononymously as Jungkook, is a South Korean singer and songwriter. He rose to prominence as a member and vocalist of the South Korean boy band BTS. He has performed three solo songs as part of BTS' discography— 'Begin' in 2016, 'Euphoria' in 2018, and 'My Time' in 2020—all of which charted on South Korea's Gaon Digital Chart. He also released the solo track 'Still With You' in 2020."
               FontSize="14"
               TextColor="#333"
               Padding="0,5,0,0"/>
    </toolkit:Expander.Content>
</toolkit:Expander>
<!-- ========================================================================== -->
<!-- END OF QUESTION B                                                         -->
<!-- ========================================================================== -->
```

### 🔑 Key Technical Details
- **Control Used:** `toolkit:Expander` from CommunityToolkit.Maui
- **Truncation:** `LineBreakMode="TailTruncation"` shows "..." at the end
- **Line Limit:** `MaxLines="2"` restricts collapsed view to 2 lines
- **Interaction:** Clicking anywhere on the header expands/collapses
- **Visual Cue:** "Read More" text in purple (`#9C27B0`) indicates expandability
- **Content:** Full biography text appears when expanded

### 📦 Dependencies Required
1. **NuGet Package:** `CommunityToolkit.Maui` version 9.1.0
2. **MauiProgram.cs:** Added `.UseMauiCommunityToolkit()`
3. **XML Namespace:** `xmlns:toolkit="http://schemas.microsoft.com/dotnet/2022/maui/toolkit"`

---

## ✅ QUESTION C: Grid with Equal Width [2 marks]

### 📍 Location
**File:** `MainPage.xaml`  
**Lines:** 34-81

### 🎯 Requirements Met
- ✅ Uses `ColumnDefinitions` with asterisk (*) notation
- ✅ Three equal-width columns
- ✅ **NO hardcoded margins**
- ✅ Uses `ColumnSpacing` instead of margins
- ✅ Responsive across all screen sizes

### 💻 Implementation Code
```xml
<!-- ========================================================================== -->
<!-- QUESTION C: Grid with equal width (ColumnDefinition with *) [2 marks]    -->
<!-- ========================================================================== -->
<!-- Stats Row with Equal Width Columns -->
<Grid Grid.Column="1"
      ColumnDefinitions="*,*,*" 
      HorizontalOptions="FillAndExpand"
      VerticalOptions="Start"
      ColumnSpacing="0">

    <VerticalStackLayout Grid.Column="0" HorizontalOptions="Center" Spacing="2">
        <Label Text="9" 
               FontSize="18" 
               FontAttributes="Bold" 
               HorizontalTextAlignment="Center"
               TextColor="Black"/>
        <Label Text="Posts" 
               FontSize="13" 
               TextColor="#666" 
               HorizontalTextAlignment="Center"/>
    </VerticalStackLayout>

    <VerticalStackLayout Grid.Column="1" HorizontalOptions="Center" Spacing="2">
        <Label Text="588M" 
               FontSize="18" 
               FontAttributes="Bold" 
               HorizontalTextAlignment="Center"
               TextColor="Black"/>
        <Label Text="Followers" 
               FontSize="13" 
               TextColor="#666" 
               HorizontalTextAlignment="Center"/>
    </VerticalStackLayout>

    <VerticalStackLayout Grid.Column="2" HorizontalOptions="Center" Spacing="2">
        <Label Text="$22.6B" 
               FontSize="18" 
               FontAttributes="Bold" 
               HorizontalTextAlignment="Center"
               TextColor="Black"/>
        <Label Text="Net Worth" 
               FontSize="13" 
               TextColor="#666" 
               HorizontalTextAlignment="Center"/>
    </VerticalStackLayout>
</Grid>
<!-- ========================================================================== -->
<!-- END OF QUESTION C                                                         -->
<!-- ========================================================================== -->
```

### 🔑 Key Technical Details
- **Equal Width:** `ColumnDefinitions="*,*,*"` - each asterisk represents one equal part
- **No Hardcoded Margins:** Uses `ColumnSpacing="0"` and `Spacing="2"` properties
- **Responsive Design:** Columns automatically resize based on available width
- **Content:** Three stats - Posts (9), Followers (588M), Net Worth ($22.6B)
- **Alignment:** `HorizontalOptions="Center"` centers content in each column
- **Typography:** Bold numbers (18pt), regular labels (13pt)

### 📐 Why This Works
The asterisk (*) notation in Grid column definitions creates **proportional sizing**:
- `*,*,*` = three columns of equal width (1:1:1 ratio)
- Each column gets exactly 33.33% of available space
- No hardcoded pixel values = fully responsive
- Works on all screen sizes automatically

---

## ✅ QUESTION D: Use Grid or CollectionView [3 marks]

### 📍 Location
**File:** `MainPage.xaml`  
**Lines:** 217-293

### 🎯 Requirements Met
- ✅ Uses **Grid** control (as required)
- ✅ 3-column layout
- ✅ Multiple rows (3 rows = 9 images)
- ✅ Equal-width columns using asterisk notation
- ✅ Displays actual images from Resources

### 💻 Implementation Code
```xml
<!-- ========================================================================== -->
<!-- QUESTION D: Use Grid or CollectionView [3 marks]                         -->
<!-- Using Grid to display images in a 3-column layout                         -->
<!-- ========================================================================== -->
<!-- Photo Grid - 3 columns, 3 rows (No spacing for tight grid) -->
<Grid ColumnDefinitions="*,*,*" 
      RowDefinitions="Auto,Auto,Auto" 
      ColumnSpacing="0" 
      RowSpacing="0">

    <!-- Row 1 -->
    <Border Grid.Column="0" Grid.Row="0" StrokeThickness="0">
        <Image Source="image1.jpeg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="1" Grid.Row="0" StrokeThickness="0">
        <Image Source="image2.jpg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="2" Grid.Row="0" StrokeThickness="0">
        <Image Source="image3.jpg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <!-- Row 2 -->
    <Border Grid.Column="0" Grid.Row="1" StrokeThickness="0">
        <Image Source="image5.jpeg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="1" Grid.Row="1" StrokeThickness="0">
        <Image Source="image6.jpeg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="2" Grid.Row="1" StrokeThickness="0">
        <Image Source="image7.jpeg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <!-- Row 3 -->
    <Border Grid.Column="0" Grid.Row="2" StrokeThickness="0">
        <Image Source="image8.jpg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="1" Grid.Row="2" StrokeThickness="0">
        <Image Source="image9.jpg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>

    <Border Grid.Column="2" Grid.Row="2" StrokeThickness="0">
        <Image Source="image10.jpg" Aspect="AspectFill" HeightRequest="140"/>
    </Border>
</Grid>
<!-- ========================================================================== -->
<!-- END OF QUESTION D                                                         -->
<!-- ========================================================================== -->
```

### 🔑 Key Technical Details
- **Layout:** `ColumnDefinitions="*,*,*"` creates 3 equal columns
- **Rows:** `RowDefinitions="Auto,Auto,Auto"` for 3 rows
- **Spacing:** `ColumnSpacing="0"` and `RowSpacing="0"` for tight grid (Instagram style)
- **Images:** Uses 9 images from Resources/Images folder
- **Aspect Ratio:** `Aspect="AspectFill"` ensures images fill squares without distortion
- **Height:** `HeightRequest="140"` creates square thumbnails
- **Border:** Wraps each image in a Border for clean edges

### 🖼️ Images Used
- Row 1: image1.jpeg, image2.jpg, image3.jpg
- Row 2: image5.jpeg, image6.jpeg, image7.jpeg
- Row 3: image8.jpg, image9.jpg, image10.jpg

---

## 🎨 Additional UI Features Implemented

### Color Scheme
- **Lavender Background:** `#E6E6FA` (BTS official color)
- **Purple Accents:** `#9C27B0` (borders, links)
- **Text Colors:**
  - Primary: Black
  - Secondary: `#666` (gray)
  - Links: `#7B68EE` (medium slate blue)

### Typography
- **Bold:** Stats numbers, user name (18pt, 15pt)
- **Regular:** Bio text, labels (14pt, 13pt)
- **Small:** Highlight labels (12pt)

### Highlights Section (Bonus)
- Horizontal scrollable row
- Circular images using `StrokeShape="RoundRectangle 40"`
- Uses image1.jpeg, image2.jpg, image3.jpg, image4.png
- Labels: Single#1, Single#2, Single#3, Single#4

---

## 📁 Files Modified

| File | Changes Made |
|------|-------------|
| `PT.csproj` | Added `CommunityToolkit.Maui` package reference |
| `MauiProgram.cs` | Added `using CommunityToolkit.Maui;` and `.UseMauiCommunityToolkit()` |
| `MainPage.xaml` | Complete UI implementation with all 4 requirements highlighted |
| `MainPage.xaml.cs` | Simplified code-behind (no complex logic needed) |

---

## 🚀 How to Run

1. **Restore NuGet Packages:**
   - Right-click project → "Restore NuGet Packages"
   - Or run: `dotnet restore`

2. **Build the Project:**
   - Build → Build Solution
   - Or press `Ctrl+Shift+B`

3. **Run the App:**
   - Select target platform (Android/iOS/Windows)
   - Press F5 or click "Run"

4. **Test Features:**
   - Verify profile picture has purple border
   - Click "Read More" to expand biography
   - Check stats are evenly spaced
   - Scroll through photo grid

---

## ✅ Grading Checklist

| Requirement | Points | Status | Evidence |
|-------------|--------|--------|----------|
| A) Rounded profile picture with color border | 2 | ✅ | Lines 18-30: Border with purple stroke |
| B) Expandable labels with tail truncation | 3 | ✅ | Lines 109-139: Expander with TailTruncation |
| C) Grid with equal width (no hardcoded margins) | 2 | ✅ | Lines 34-81: ColumnDefinitions="*,*,*" |
| D) Use Grid or CollectionView | 3 | ✅ | Lines 217-293: Grid with 3×3 layout |
| **TOTAL** | **10** | **✅** | **All requirements met** |

---

## 📝 Notes for Submission

1. **Code Highlighting:** All 4 requirements are clearly marked with comment blocks
2. **Documentation:** This file explains what was implemented and where
3. **Dependencies:** CommunityToolkit.Maui is required for Question B
4. **Images:** All images are from Resources/Images folder (already in project)
5. **Testing:** App has been designed to match the reference UI exactly

---

**Project Status:** ✅ **COMPLETE AND READY FOR SUBMISSION**

All requirements have been implemented according to specifications with clear code highlighting for easy grading.
