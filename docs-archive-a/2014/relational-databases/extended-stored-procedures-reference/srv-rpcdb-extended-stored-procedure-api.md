---
title: srv_rpcdb (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684750"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="045f7-102">srv_rpcdb (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="045f7-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="045f7-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="045f7-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="045f7-104">Retorna o componente de nome de banco de dados para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="045f7-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="045f7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="045f7-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="045f7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="045f7-106">Arguments</span></span>  
 <span data-ttu-id="045f7-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="045f7-107">*srvproc*</span></span>  
 <span data-ttu-id="045f7-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="045f7-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="045f7-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="045f7-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="045f7-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="045f7-110">*len*</span></span>  
 <span data-ttu-id="045f7-111">É um ponteiro para uma variável `int` que recebe o comprimento do nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="045f7-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="045f7-112">Se *len* for NULL, o tamanho do nome do banco de dados não será retornado.</span><span class="sxs-lookup"><span data-stu-id="045f7-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="045f7-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="045f7-113">Returns</span></span>  
 <span data-ttu-id="045f7-114">Um ponteiro DBCHAR para a cadeia de caracteres com terminação nula para a parte do nome do banco de dados do procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="045f7-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="045f7-115">Se não houver nenhum procedimento armazenado remoto atual, NULL será retornado e o parâmetro *len* será definido como -1.</span><span class="sxs-lookup"><span data-stu-id="045f7-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="045f7-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="045f7-116">Remarks</span></span>  
 <span data-ttu-id="045f7-117">Esta função retorna somente o componente de banco de dados do nome de objeto de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="045f7-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="045f7-118">Isto não inclui os especificadores opcionais para proprietário, nome do procedimento armazenado remoto e número do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="045f7-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="045f7-119">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="045f7-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="045f7-120">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="045f7-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
