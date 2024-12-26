# qr-code-scanner-using-python-
import qrcode

# Function to generate and save QR code
def generate_qr_code(data, filename):
   
    qr = qrcode.QRCode(
        version=1,  # controls the size of the QR code (1 is the smallest size)
        error_correction=qrcode.constants.ERROR_CORRECT_L,  # Error correction level
        box_size=10,  # Size of each box in the QR code
        border=4,  # Thickness of the border (in boxes)
    )
    
    qr.add_data(data)
    qr.make(fit=True)
    
    img = qr.make_image(fill='black', back_color='white')
    img.save(filename)

if __name__ == "__main__":
    data = input("Enter the data for the QR code (text, URL, etc.): ")
    filename = input("Enter the filename to save the QR code image (e.g., qr_code.png): ")
  
    generate_qr_code(data, filename)
    
    print(f"QR code has been generated and saved as {filename}.")


