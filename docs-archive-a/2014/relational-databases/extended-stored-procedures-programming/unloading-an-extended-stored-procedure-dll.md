---
title: Descarregando uma DLL de procedimento armazenado estendido | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bd4855390e95d949ab769d6567d6f106959dcde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568570"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a><span data-ttu-id="46826-102">Descarregando uma DLL de procedimento armazenado estendido</span><span class="sxs-lookup"><span data-stu-id="46826-102">Unloading an Extended Stored Procedure DLL</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="46826-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="46826-103">Use CLR Integration instead.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="46826-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]carrega uma DLL de procedimento armazenado estendido assim que uma chamada é feita para uma das funções da dll.</span><span class="sxs-lookup"><span data-stu-id="46826-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads an extended stored procedure DLL as soon as a call is made to one of the functions of the DLL.</span></span> <span data-ttu-id="46826-105">A DLL permanece carregada até o servidor ser desligado ou até o administrador do sistema usar a instrução DBCC para descarregá-la.</span><span class="sxs-lookup"><span data-stu-id="46826-105">The DLL remains loaded until the server is shut down or until the system administrator uses the DBCC statement to unload it.</span></span> <span data-ttu-id="46826-106">Por exemplo, esse comando descarrega o **xp_hello.dll**, permitindo que o administrador do sistema Copie uma versão mais recente desse arquivo para o diretório sem desligar o servidor:</span><span class="sxs-lookup"><span data-stu-id="46826-106">For example, this command unloads the **xp_hello.dll**, allowing the system administrator to copy a newer version of this file to the directory without shutting down the server:</span></span>  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a><span data-ttu-id="46826-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46826-107">See Also</span></span>  
 [<span data-ttu-id="46826-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="46826-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dllname-free-transact-sql)  
  
  
