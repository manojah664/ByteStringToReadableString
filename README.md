# ByteStringToReadableString
conversion of byteString to readable string

export const DownPdf = async(data)=>{

    const bstr = atob(data.docByteString);
          let n = bstr.length;
          const u8arr = new Uint8Array(n);
          while (n--) {
              u8arr[n] = bstr.charCodeAt(n);
          }
		  saveAs(new File([u8arr], data.docName, {type: data.docType}));
      
