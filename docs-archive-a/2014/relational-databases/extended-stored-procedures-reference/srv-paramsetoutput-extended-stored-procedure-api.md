---
title: srv_paramsetoutput (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570018"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="3b067-102">srv_paramsetoutput (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="3b067-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3b067-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="3b067-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="3b067-104">Define o valor de um parâmetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="3b067-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="3b067-105">Essa função substitui a função **srv_paramset**.</span><span class="sxs-lookup"><span data-stu-id="3b067-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b067-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b067-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b067-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3b067-107">Arguments</span></span>  
 <span data-ttu-id="3b067-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="3b067-108">*srvproc*</span></span>  
 <span data-ttu-id="3b067-109">É um identificador para uma conexão do cliente.</span><span class="sxs-lookup"><span data-stu-id="3b067-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="3b067-110">*n*</span><span class="sxs-lookup"><span data-stu-id="3b067-110">*n*</span></span>  
 <span data-ttu-id="3b067-111">É o número ordinal do parâmetro que será definido.</span><span class="sxs-lookup"><span data-stu-id="3b067-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="3b067-112">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="3b067-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="3b067-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="3b067-113">*pbData*</span></span>  
 <span data-ttu-id="3b067-114">É um ponteiro para o valor dos dados que será enviado de volta ao cliente como um parâmetro de retorno do procedimento.</span><span class="sxs-lookup"><span data-stu-id="3b067-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="3b067-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="3b067-115">*cbLen*</span></span>  
 <span data-ttu-id="3b067-116">É o comprimento real dos dados que serão retornados.</span><span class="sxs-lookup"><span data-stu-id="3b067-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="3b067-117">Se o tipo de dados do parâmetro especificar valores de um tamanho constante e não permitir valores nulos (por exemplo, *srvbit* ou *srvint1*), *cbLen* será ignorado.</span><span class="sxs-lookup"><span data-stu-id="3b067-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="3b067-118">Um valor igual a 0 significará dados de comprimento zero se *fNull* for FALSE.</span><span class="sxs-lookup"><span data-stu-id="3b067-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="3b067-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="3b067-119">*fNull*</span></span>  
 <span data-ttu-id="3b067-120">É um sinalizador que indica se o valor do parâmetro de retorno é o NULL.</span><span class="sxs-lookup"><span data-stu-id="3b067-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="3b067-121">Defina este sinalizador como TRUE se o parâmetro for definido como NULL.</span><span class="sxs-lookup"><span data-stu-id="3b067-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="3b067-122">O valor padrão é FALSE.</span><span class="sxs-lookup"><span data-stu-id="3b067-122">The default value is FALSE.</span></span> <span data-ttu-id="3b067-123">Se *fNull* for definido como TRUE, *cbLen* deverá ser definido como 0 ou a função falhará.</span><span class="sxs-lookup"><span data-stu-id="3b067-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3b067-124">Retornos</span><span class="sxs-lookup"><span data-stu-id="3b067-124">Returns</span></span>  
 <span data-ttu-id="3b067-125">Se as informações de parâmetro tiverem sido definidas com êxito, SUCCEED será retornado. Caso contrário, o retorno será FAIL.</span><span class="sxs-lookup"><span data-stu-id="3b067-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="3b067-126">FAIL é retornado quando</span><span class="sxs-lookup"><span data-stu-id="3b067-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="3b067-127">o parâmetro não é um parâmetro de retorno ou</span><span class="sxs-lookup"><span data-stu-id="3b067-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="3b067-128">o argumento *cbLen* é inválido.</span><span class="sxs-lookup"><span data-stu-id="3b067-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b067-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="3b067-129">Remarks</span></span>  
 <span data-ttu-id="3b067-130">**Observação de segurança** Você deve examinar detalhadamente o código-fonte de procedimentos armazenados estendidos e testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="3b067-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="3b067-131">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="3b067-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
