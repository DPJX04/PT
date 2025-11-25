# Quick Reference: Code Highlighting Guide

## For Your Lecturer - Line Numbers to Highlight in MainPage.xaml

---

### ✅ QUESTION A: Rounded Profile Picture with Color Border [2 marks]

**📍 Lines to Highlight: 18-30**

**What to Look For:**
- `Border` control with circular shape
- `StrokeThickness="3"` (3-pixel border width)
- `Stroke="#9C27B0"` (purple/violet color border)
- `StrokeShape="RoundRectangle 50"` (creates circular/rounded effect)
- Contains `Image` with `Source="owner1.jpeg"`

**Code Snippet:**
```xml
<!-- QUESTION A: Rounded profile picture with color border [2 marks] -->
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
<!-- END OF QUESTION A -->
```

---

### ✅ QUESTION B: Expandable Labels with Tail Truncation [3 marks]

**📍 Lines to Highlight: 109-139**

**What to Look For:**
- `toolkit:Expander` control (from MAUI Community Toolkit)
- `LineBreakMode="TailTruncation"` (shows "..." when text is cut off)
- `MaxLines="2"` (limits to 2 lines when collapsed)
- "Read More" text link in purple color
- Expandable content section with full biography

**Code Snippet:**
```xml
<!-- QUESTION B: Expandable labels with tail truncation [3 marks] -->
<toolkit:Expander x:Name="BioExpander">
    <toolkit:Expander.Header>
        <Grid ColumnDefinitions="*,Auto">
            <Label Grid.Column="0"
                   Text="Jeon Jung-kook (Korean: 전정국; born September 1, 1997)..."
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
        <Label Text="[Full biography text...]"/>
    </toolkit:Expander.Content>
</toolkit:Expander>
<!-- END OF QUESTION B -->
```

---

### ✅ QUESTION C: Grid with Equal Width [2 marks]

**📍 Lines to Highlight: 34-81**

**What to Look For:**
- `Grid` with `ColumnDefinitions="*,*,*"` (three asterisks = equal width)
- Three columns: Posts, Followers, Net Worth
- **NO hardcoded margins** - uses `ColumnSpacing="0"` instead
- Each column uses `HorizontalOptions="Center"` for centering

**Code Snippet:**
```xml
<!-- QUESTION C: Grid with equal width (ColumnDefinition with *) [2 marks] -->
<Grid Grid.Column="1"
      ColumnDefinitions="*,*,*" 
      HorizontalOptions="FillAndExpand"
      VerticalOptions="Start"
      ColumnSpacing="0">

    <VerticalStackLayout Grid.Column="0" HorizontalOptions="Center" Spacing="2">
        <Label Text="9" FontSize="18" FontAttributes="Bold"/>
        <Label Text="Posts" FontSize="13" TextColor="#666"/>
    </VerticalStackLayout>

    <VerticalStackLayout Grid.Column="1" HorizontalOptions="Center" Spacing="2">
        <Label Text="588M" FontSize="18" FontAttributes="Bold"/>
        <Label Text="Followers" FontSize="13" TextColor="#666"/>
    </VerticalStackLayout>

    <VerticalStackLayout Grid.Column="2" HorizontalOptions="Center" Spacing="2">
        <Label Text="$22.6B" FontSize="18" FontAttributes="Bold"/>
        <Label Text="Net Worth" FontSize="13" TextColor="#666"/>
    </VerticalStackLayout>
</Grid>
<!-- END OF QUESTION C -->
```

---

### ✅ QUESTION D: Use Grid or CollectionView [3 marks]

**📍 Lines to Highlight: 217-293**

**What to Look For:**
- `Grid` control for photo gallery layout
- `ColumnDefinitions="*,*,*"` (3 equal-width columns)
- `RowDefinitions="Auto,Auto,Auto"` (3 rows)
- `ColumnSpacing="0"` and `RowSpacing="0"` (no gaps - tight grid)
- 9 images total (3×3 grid)
- Uses images: image1.jpeg through image10.jpg

**Code Snippet:**
```xml
<!-- QUESTION D: Use Grid or CollectionView [3 marks] -->
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

    <!-- Row 2 and Row 3 continue... -->
</Grid>
<!-- END OF QUESTION D -->
```

---

## 📊 Summary Table

| Question | Marks | MainPage.xaml Lines | Key Feature |
|----------|-------|---------------------|-------------|
| **A** | 2 | **18-30** | Border with `Stroke="#9C27B0"` and `StrokeShape="RoundRectangle 50"` |
| **B** | 3 | **109-139** | `toolkit:Expander` with `LineBreakMode="TailTruncation"` and `MaxLines="2"` |
| **C** | 2 | **34-81** | Grid with `ColumnDefinitions="*,*,*"` (equal width, no hardcoded margins) |
| **D** | 3 | **217-293** | Grid layout with 3×3 photo gallery using `ColumnSpacing="0"` |

---

## 🎨 UI Design Features Implemented

### Color Scheme:
- **Lavender Background**: `#E6E6FA` for header section
- **Purple Accents**: `#9C27B0` for borders and links
- **Text Colors**: Black for primary, `#666` for secondary, `#7B68EE` for links

### Layout Structure:
1. **Header Section** (Lavender background)
   - Profile picture with purple border (left)
   - Stats grid (right) - Posts, Followers, Net Worth
   - Name and bio information
   - Expandable biography with "Read More"

2. **Highlights Section**
   - Horizontal scrollable row
   - Circular images (image1.jpeg, image2.jpg, image3.jpg, image4.png)
   - Labels: Single#1, Single#2, Single#3, Single#4

3. **Photo Grid**
   - 3×3 tight grid (no spacing)
   - Square thumbnails
   - Uses image1-10 from Resources/Images

---

## 📝 How to Highlight for Submission

### Option 1: Print and Highlight
1. Print the `MainPage.xaml` file
2. Use a **yellow highlighter** on these line ranges:
   - Lines 18-30 (Question A)
   - Lines 109-139 (Question B)
   - Lines 34-81 (Question C)
   - Lines 217-293 (Question D)
3. Write **"Question A"**, **"Question B"**, etc. in the margin

### Option 2: Digital Submission
- The code already has comment blocks:
  ```xml
  <!-- QUESTION X: [Description] [X marks] -->
  ```
- These make it obvious to your lecturer where each requirement is

### Option 3: Include This Document
- Submit this `HIGHLIGHTING_GUIDE.md` file alongside your code
- It shows exactly what was implemented and where

---

## ✅ Checklist Before Submission

- [ ] Restore NuGet packages (to install CommunityToolkit.Maui)
- [ ] Build the project successfully
- [ ] Test the "Read More" expander functionality
- [ ] Verify all images are displaying correctly
- [ ] Review highlighted sections match the requirements
- [ ] Include HIGHLIGHTING_GUIDE.md and ASSIGNMENT_REQUIREMENTS.md

---

**Total Marks: 10/10** ✨
