---
title: "IDiaSession::findInlineeLinesByLinenum | Microsoft Docs"
ms.custom: ""
ms.date: 11/15/2016
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSession::findInlineeLinesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Retrieves an enumeration that allows a client to iterate through the line number information of all functions that are inlined, directly or indirectly, in the specified source file and line number.  
  
## Syntax  
  
```cpp#  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### Parameters  
 `compiland`  
 [in] An [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) object that represents the compiland in which to search for the line numbers. This parameter cannot be `NULL`.  
  
 `file`  
 [in] An [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) object that represents the source file in which to search. This parameter cannot be `NULL`.  
  
 `linenum`  
 [in] Specifies a one-based line number.  
  
> [!NOTE]
>  You cannot use zero to specify all lines (use the [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md) method to find all lines).  
  
 `column`  
 [in] Specifies the column number. Use zero to specify all columns. A column is a byte offset into a line.  
  
 `ppResult`  
 [out] Returns an [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) object that contains a list of the line numbers that were retrieved.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum Enumeration](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)


