---
title: srv_paraminfo (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685715"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="94024-102">srv_paraminfo (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="94024-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="94024-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="94024-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="94024-104">Retorna informações sobre um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94024-104">Returns information about a parameter.</span></span> <span data-ttu-id="94024-105">Essa função substitui as seguintes funções: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) e [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="94024-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="94024-106">**srv_paraminfo** dá suporte aos tipos de dados em [Tipos de Dados](data-types-extended-stored-procedure-api.md) e dados de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="94024-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94024-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="94024-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="94024-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94024-108">Arguments</span></span>  
 <span data-ttu-id="94024-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="94024-109">*srvproc*</span></span>  
 <span data-ttu-id="94024-110">Um identificador para uma conexão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94024-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="94024-111">*n*</span><span class="sxs-lookup"><span data-stu-id="94024-111">*n*</span></span>  
 <span data-ttu-id="94024-112">O número ordinal do parâmetro para ser definido.</span><span class="sxs-lookup"><span data-stu-id="94024-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="94024-113">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="94024-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="94024-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="94024-114">*pbType*</span></span>  
 <span data-ttu-id="94024-115">O tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94024-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="94024-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="94024-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="94024-117">Ponteiro para o comprimento máximo do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94024-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="94024-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="94024-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="94024-119">Ponteiro para o comprimento real do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94024-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="94024-120">Um valor igual a 0 (\**pcbActualLen* == 0) significa dados de comprimento zero se \**pfNull* está definida como FALSE.</span><span class="sxs-lookup"><span data-stu-id="94024-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="94024-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="94024-121">*pbData*</span></span>  
 <span data-ttu-id="94024-122">Ponteiro para o buffer para obter dados de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94024-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="94024-123">Se *pbData* não for NULL, a API de Procedimento Armazenado Estendido gravará \**pcbActualLen* bytes de dados em \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="94024-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="94024-124">Se *pbData* for NULL, nenhum dado será gravado em \**pbData*, mas a função retorna \**pbType*, \**pcbMaxLen*, \**pcbActualLen* e \**pfNull*.</span><span class="sxs-lookup"><span data-stu-id="94024-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="94024-125">A memória para este buffer deve ser gerenciada pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94024-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="94024-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="94024-126">*pfNull*</span></span>  
 <span data-ttu-id="94024-127">Ponteiro para um sinalizador nulo.</span><span class="sxs-lookup"><span data-stu-id="94024-127">Pointer to a null flag.</span></span><span data-ttu-id="94024-128">\ **pfNull* será definido como TRUE se o valor do parâmetro for NULL.</span><span class="sxs-lookup"><span data-stu-id="94024-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="94024-129">Retornos</span><span class="sxs-lookup"><span data-stu-id="94024-129">Returns</span></span>  
 <span data-ttu-id="94024-130">Se a informações de parâmetro tiverem sido obtidas com êxito, SUCCEED será retornado. Caso contrário, o retorno será FAIL.</span><span class="sxs-lookup"><span data-stu-id="94024-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="94024-131">FAIL será retornado quando não houver procedimento armazenado remoto atual e quando não houver parâmetro para o *n*-ésimo procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="94024-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94024-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="94024-132">Remarks</span></span>  
 <span data-ttu-id="94024-133">**Observação de segurança** Você deve examinar detalhadamente o código-fonte de procedimentos armazenados estendidos e testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="94024-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="94024-134">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="94024-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94024-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94024-135">See Also</span></span>  
 [<span data-ttu-id="94024-136">Referência do programador de procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="94024-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
