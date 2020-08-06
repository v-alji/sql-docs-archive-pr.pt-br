---
title: srv_pfieldex (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571395"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="fc76d-102">srv_pfieldex (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="fc76d-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fc76d-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="fc76d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fc76d-104">Retorna um ponteiro para dados que contêm o campo SRV_PROC solicitado.</span><span class="sxs-lookup"><span data-stu-id="fc76d-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc76d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fc76d-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc76d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fc76d-106">Arguments</span></span>  
 <span data-ttu-id="fc76d-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="fc76d-107">*srvproc*</span></span>  
 <span data-ttu-id="fc76d-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="fc76d-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="fc76d-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="fc76d-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="fc76d-110">*campo*</span><span class="sxs-lookup"><span data-stu-id="fc76d-110">*field*</span></span>  
 <span data-ttu-id="fc76d-111">Especifica o campo *srvproc* a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="fc76d-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="fc76d-112">Campo</span><span class="sxs-lookup"><span data-stu-id="fc76d-112">Field</span></span>|<span data-ttu-id="fc76d-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="fc76d-113">Description</span></span>|<span data-ttu-id="fc76d-114">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="fc76d-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="fc76d-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="fc76d-115">SRV_MSGLCID</span></span>|<span data-ttu-id="fc76d-116">LCID de mensagem da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fc76d-116">Current session message LCID.</span></span>|<span data-ttu-id="fc76d-117">ULONG \*</span><span class="sxs-lookup"><span data-stu-id="fc76d-117">ULONG\*</span></span>|  
|<span data-ttu-id="fc76d-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="fc76d-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="fc76d-119">Nome de instância (se nomeado); caso contrário, retorna NULL.</span><span class="sxs-lookup"><span data-stu-id="fc76d-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="fc76d-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="fc76d-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="fc76d-121">*Len*</span><span class="sxs-lookup"><span data-stu-id="fc76d-121">*len*</span></span>  
 <span data-ttu-id="fc76d-122">É um ponteiro para uma variável **int** que contém o tamanho do valor de *field* retornado, em bytes.</span><span class="sxs-lookup"><span data-stu-id="fc76d-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="fc76d-123">Se *len* for NULL, o tamanho não será retornado.</span><span class="sxs-lookup"><span data-stu-id="fc76d-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="fc76d-124">Quando NULL é retornado, \**len* é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="fc76d-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fc76d-125">Retornos</span><span class="sxs-lookup"><span data-stu-id="fc76d-125">Returns</span></span>  
 <span data-ttu-id="fc76d-126">Um ponteiro para dados cujo tipo depende de *field*.</span><span class="sxs-lookup"><span data-stu-id="fc76d-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="fc76d-127">NULL é retornado quando *len* é NULL ou *srvproc* é NULL.</span><span class="sxs-lookup"><span data-stu-id="fc76d-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="fc76d-128">Se o *field* for desconhecido, NULL será retornado.</span><span class="sxs-lookup"><span data-stu-id="fc76d-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="fc76d-129">Quando NULL é retornado, \**len* é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="fc76d-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc76d-130">O buffer retornado pelo servidor deve ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="fc76d-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="fc76d-131">Caso contrário, o estado do servidor pode estar corrompido.</span><span class="sxs-lookup"><span data-stu-id="fc76d-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc76d-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="fc76d-132">Remarks</span></span>  
 <span data-ttu-id="fc76d-133">**Observação de segurança** Você deve examinar detalhadamente o código-fonte de procedimentos armazenados estendidos e testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="fc76d-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="fc76d-134">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="fc76d-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
