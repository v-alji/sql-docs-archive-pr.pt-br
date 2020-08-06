---
title: srv_rpcname (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685704"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="f2dad-102">srv_rpcname (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="f2dad-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f2dad-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="f2dad-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f2dad-104">Retorna o componente de nome de procedimento para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="f2dad-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2dad-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f2dad-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2dad-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f2dad-106">Arguments</span></span>  
 <span data-ttu-id="f2dad-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f2dad-107">*srvproc*</span></span>  
 <span data-ttu-id="f2dad-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu o procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="f2dad-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="f2dad-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="f2dad-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="f2dad-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="f2dad-110">*len*</span></span>  
 <span data-ttu-id="f2dad-111">É um ponteiro para uma variável inteira que recebe o comprimento do nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f2dad-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="f2dad-112">Se *len* for NULL, o comprimento do nome do procedimento armazenado remoto não será retornado.</span><span class="sxs-lookup"><span data-stu-id="f2dad-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f2dad-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="f2dad-113">Returns</span></span>  
 <span data-ttu-id="f2dad-114">Um ponteiro DBCHAR para a cadeia de caracteres com terminação nula do componente de nome de procedimento armazenado remoto do procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="f2dad-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="f2dad-115">Se não houver um procedimento armazenado remoto atual, NULL será retornado e *len* será definido como -1.</span><span class="sxs-lookup"><span data-stu-id="f2dad-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2dad-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="f2dad-116">Remarks</span></span>  
 <span data-ttu-id="f2dad-117">Essa função retorna apenas o nome do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="f2dad-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="f2dad-118">Ela não inclui os especificadores opcionais para proprietário, nome do banco de dados e número do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="f2dad-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="f2dad-119">Como é válido chamar **srv_rpcname** quando não existe um procedimento armazenado remoto (nenhum erro informativo ocorre), essa função fornece um método para determinar se um procedimento armazenado remoto existe.</span><span class="sxs-lookup"><span data-stu-id="f2dad-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f2dad-120">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="f2dad-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f2dad-121">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f2dad-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
