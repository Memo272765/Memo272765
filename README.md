from fpdf import FPDF

# Create instance of FPDF class
pdf = FPDF()

# Add a page
pdf.add_page()

# Set title and fonts
pdf.set_font("Arial", 'B', 16)
pdf.cell(200, 10, txt="Freud's Psychosexual Development Stages", ln=True, align='C')

# Add a line break
pdf.ln(10)

# Set the font for the table header
pdf.set_font("Arial", 'B', 12)

# Define the header
header = ["Stage", "Age", "Conflict", "Strengths", "Important Events", "Relationship", "Fixation", "Task", "Desired Outcome"]

# Set column widths
col_widths = [22, 18, 25, 25, 35, 25, 25, 25, 45]

# Add the table header
for i, col_name in enumerate(header):
    pdf.cell(col_widths[i], 10, col_name, 1, 0, 'C')
pdf.ln(10)

# Set the font for the table content
pdf.set_font("Arial", '', 10)

# Define the data
data = [
    ["Oral", "0-1 year", "Dependence on the mouth for pleasure and comfort", "Trust, security", "Breastfeeding, putting objects in mouth", "Mother", "Oral fixation (e.g., smoking, overeating)", "Weaning", "Developing trust and comfort in relationships"],
    ["Anal", "1-3 years", "Control over bodily excretions", "Independence, control", "Toilet training", "Parents", "Anal fixation (e.g., orderliness, messiness)", "Toilet training", "Developing a sense of autonomy and control"],
    ["Phallic", "3-6 years", "Discovering gender differences and Oedipal conflict", "Gender identity, moral values", "Identifying gender differences", "Parents (Oedipal conflict)", "Phallic fixation (e.g., vanity, recklessness)", "Resolving the Oedipal/Electra complex", "Establishing a healthy sexual identity"],
    ["Latency", "6 years - puberty", "Dormant sexual feelings and focus on skills", "Competence, friendships", "School activities, learning", "Friends, teachers", "Fixation generally does not occur in this stage", "Developing communication and self-confidence", "Developing social and intellectual skills"],
    ["Genital", "Puberty onwards", "Revival of sexual interests and mature relationships", "Sexual maturity, healthy relationships", "Forming romantic relationships", "Romantic partners", "Fixation can result in difficulties in relationships", "Forming intimate relationships", "Achieving mature sexual intimacy and well-rounded relationships"]
]

# Add the data to the table
for row in data:
    for i, item in enumerate(row):
        pdf.cell(col_widths[i], 10, item, 1, 0, 'C')
    pdf.ln(10)

# Save the pdf with name .pdf
pdf_file_path = "Freud_Psychosexual_Development_Stages.pdf"
pdf.output(pdf_file_path)
