---
title: srv_alloc (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571400"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="7fd13-102">srv_alloc (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="7fd13-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7fd13-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="7fd13-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7fd13-104">Aloca memória dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="7fd13-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd13-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7fd13-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7fd13-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7fd13-106">Arguments</span></span>  
 <span data-ttu-id="7fd13-107">*size*</span><span class="sxs-lookup"><span data-stu-id="7fd13-107">*size*</span></span>  
 <span data-ttu-id="7fd13-108">Especifica o número de bytes para alocar.</span><span class="sxs-lookup"><span data-stu-id="7fd13-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7fd13-109">Retornos</span><span class="sxs-lookup"><span data-stu-id="7fd13-109">Returns</span></span>  
 <span data-ttu-id="7fd13-110">Um ponteiro para o espaço recentemente alocado.</span><span class="sxs-lookup"><span data-stu-id="7fd13-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="7fd13-111">Se *size* bytes não puderem ser alocados, um ponteiro nulo será retornado.</span><span class="sxs-lookup"><span data-stu-id="7fd13-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fd13-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="7fd13-112">Remarks</span></span>  
 <span data-ttu-id="7fd13-113">A função **srv_alloc** é equivalente à função **GlobalAlloc** da API do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7fd13-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="7fd13-114">Funções normais de gerenciamento de memória em tempo de execução da API C do Windows podem ser usadas em um aplicativo de API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="7fd13-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7fd13-115">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="7fd13-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7fd13-116">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7fd13-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
