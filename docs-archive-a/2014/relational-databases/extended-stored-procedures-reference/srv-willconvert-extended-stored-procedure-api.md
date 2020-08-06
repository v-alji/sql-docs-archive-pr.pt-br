---
title: srv_willconvert (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685702"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="281ce-102">srv_willconvert (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="281ce-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="281ce-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="281ce-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="281ce-104">Determina se uma conversão de tipo de dados específica está disponível na Biblioteca ODS.</span><span class="sxs-lookup"><span data-stu-id="281ce-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281ce-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="281ce-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="281ce-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="281ce-106">Arguments</span></span>  
 <span data-ttu-id="281ce-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="281ce-107">*srctype*</span></span>  
 <span data-ttu-id="281ce-108">Indica o tipo dos dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="281ce-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="281ce-109">Este parâmetro pode ser qualquer dos tipos de dados de API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="281ce-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="281ce-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="281ce-110">*desttype*</span></span>  
 <span data-ttu-id="281ce-111">Indica o tipo de dados no qual os dados de origem são convertidos.</span><span class="sxs-lookup"><span data-stu-id="281ce-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="281ce-112">Este parâmetro pode ser qualquer dos tipos de dados de API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="281ce-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="281ce-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="281ce-113">Returns</span></span>  
 <span data-ttu-id="281ce-114">TRUE se houver suporte para a conversão de tipo de dados; FALSE se não houver suporte para a conversão de tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="281ce-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="281ce-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="281ce-115">Remarks</span></span>  
 <span data-ttu-id="281ce-116">Para obter uma descrição de cada tipo de dados, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="281ce-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="281ce-117">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="281ce-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="281ce-118">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="281ce-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281ce-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="281ce-119">See Also</span></span>  
 [<span data-ttu-id="281ce-120">srv_convert &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="281ce-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
