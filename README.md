# File-Shares

#just note
import argparse
import textwrap
import base64

def main():
    parser = argparse.ArgumentParser(description='EDecrypt', formatter_class=argparse.RawDescriptionHelpFormatter,epilog=textwrap.dedent('''Example:
    edecrypt.py encrypt -m <method> -t  "text message"
    edecrypt.py decrypt -m <method> -t  "cyber text"
    '''))
    subparser = parser.add_subparsers(dest='command',help='Choose encrypt or decrypt')
    encrypt_parser = subparser.add_parser("encrypt",help="Encrypt the message")
    encrypt_parser.add_argument('-m', '--method', required=True, choices=['base64','aes256,'] ,help='Encryption method')
    encrypt_parser.add_argument('-t', '--text', required=True, help='Text message')
    decrypt_parser = subparser.add_parser("decrypt",help="Decrypt the cyber text")
    decrypt_parser.add_argument('-m', '--method', required=True, choices=['base64','rot16'], help='Decryption method')
    decrypt_parser.add_argument('-t', '--text', required=True, help='Cyber text')



    args = parser.parse_args()
    if args.command=="encrypt":
        print(f"you chose encryption:  {args}")
        print(f"this is message: {args.text}")
    elif args.command=="decrypt":
        print(f"you chose decrptioin:  {args}")
    #if args.listen:
     #   buffer = ''
    #else:
    #    buffer = sys.stdin.read()
    #nc = NetCat(args, buffer.encode())
    #nc.run()

def encryption():



def decryption():


    

if __name__=="__main__":
	main()
