---
title: srv_setcollen (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e3023e2ac239e074656329da7d8af3aba3afa88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679958"
---
# <a name="srv_setcollen-extended-stored-procedure-api"></a><span data-ttu-id="eaccb-102">srv_setcollen (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="eaccb-102">srv_setcollen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="eaccb-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="eaccb-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="eaccb-104">Especifica o comprimento dos dados em bytes de uma coluna de comprimento variável ou de uma coluna que aceita valores NULL.</span><span class="sxs-lookup"><span data-stu-id="eaccb-104">Specifies the current data length in bytes of a variable-length column or a column that allows NULL values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaccb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eaccb-105">Syntax</span></span>  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="eaccb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eaccb-106">Arguments</span></span>  
 <span data-ttu-id="eaccb-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="eaccb-107">*srvproc*</span></span>  
 <span data-ttu-id="eaccb-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="eaccb-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="eaccb-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="eaccb-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="eaccb-110">*column*</span><span class="sxs-lookup"><span data-stu-id="eaccb-110">*column*</span></span>  
 <span data-ttu-id="eaccb-111">Indica o número da coluna para a qual o comprimento dos dados está sendo especificado.</span><span class="sxs-lookup"><span data-stu-id="eaccb-111">Indicates the number of the column for which the data length is being specified.</span></span> <span data-ttu-id="eaccb-112">As colunas são numeradas a partir de 1.</span><span class="sxs-lookup"><span data-stu-id="eaccb-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="eaccb-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="eaccb-113">*len*</span></span>  
 <span data-ttu-id="eaccb-114">Indica o comprimento, em bytes, dos dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="eaccb-114">Indicates the length, in bytes, of the column data.</span></span> <span data-ttu-id="eaccb-115">Um comprimento igual a 0 significa que o valor dos dados da coluna é nulo.</span><span class="sxs-lookup"><span data-stu-id="eaccb-115">A length of 0 means the column data value is null.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="eaccb-116">Retornos</span><span class="sxs-lookup"><span data-stu-id="eaccb-116">Returns</span></span>  
 <span data-ttu-id="eaccb-117">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="eaccb-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaccb-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="eaccb-118">Remarks</span></span>  
 <span data-ttu-id="eaccb-119">Cada coluna da linha deve ser definida primeiro com **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="eaccb-119">Each column of the row must first be defined with **srv_describe**.</span></span> <span data-ttu-id="eaccb-120">O tamanho dos dados da coluna é definido pela última chamada a **srv_describe** ou **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="eaccb-120">The column data length is set by the last call to **srv_describe** or **srv_setcollen**.</span></span> <span data-ttu-id="eaccb-121">Se os dados de comprimento variável (dados que terminam em nulo) forem alterados em uma linha, **srv_setcollen** deverá ser usado para defini-los com o novo tamanho antes de chamar **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="eaccb-121">If variable-length data (null-terminated data) changes for a row, **srv_setcollen** must be used to set it to the new length before calling **srv_sendrow**.</span></span> <span data-ttu-id="eaccb-122">No caso de uma coluna que aceita valores nulos, **srv_describe** deve ter sido chamado com *desttype* definido com um tipo de dados que aceita nulos (como SRVINTN) e dados nulos são especificados chamando **srv_setcollen** com *len* definido como 0.</span><span class="sxs-lookup"><span data-stu-id="eaccb-122">For a column that allows null values, **srv_describe** must have been called with *desttype* set to a data type that allows nulls (like SRVINTN) and null data is specified by calling **srv_setcollen** with *len* set to 0.</span></span> <span data-ttu-id="eaccb-123">Os dados com comprimento zero não podem ser especificados com a API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="eaccb-123">Zero length data cannot be specified using the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="eaccb-124">Observe que quando o tipo de dados da coluna tem comprimento variável, *len* não é verificado.</span><span class="sxs-lookup"><span data-stu-id="eaccb-124">Note that when the data type of the column is variable-length, *len* is not checked.</span></span> <span data-ttu-id="eaccb-125">Essa função retornará FAIL se for chamada para uma coluna de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="eaccb-125">This function returns FAIL if called for a fixed-length column.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eaccb-126">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="eaccb-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="eaccb-127">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="eaccb-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaccb-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eaccb-128">See Also</span></span>  
 [<span data-ttu-id="eaccb-129">srv_describe &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="eaccb-129">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
