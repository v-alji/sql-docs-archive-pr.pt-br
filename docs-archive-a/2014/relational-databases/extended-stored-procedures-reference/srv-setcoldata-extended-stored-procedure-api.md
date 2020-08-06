---
title: srv_setcoldata (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684749"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="8da2c-102">srv_setcoldata (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="8da2c-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8da2c-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="8da2c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8da2c-104">Especifica o endereço atual dos dados de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="8da2c-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da2c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8da2c-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8da2c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8da2c-106">Arguments</span></span>  
 <span data-ttu-id="8da2c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="8da2c-107">*srvproc*</span></span>  
 <span data-ttu-id="8da2c-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="8da2c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="8da2c-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="8da2c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="8da2c-110">*column*</span><span class="sxs-lookup"><span data-stu-id="8da2c-110">*column*</span></span>  
 <span data-ttu-id="8da2c-111">Indica o número da coluna para a qual o endereço está sendo especificado.</span><span class="sxs-lookup"><span data-stu-id="8da2c-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="8da2c-112">As colunas são numeradas a partir de 1.</span><span class="sxs-lookup"><span data-stu-id="8da2c-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="8da2c-113">*data*</span><span class="sxs-lookup"><span data-stu-id="8da2c-113">*data*</span></span>  
 <span data-ttu-id="8da2c-114">É um ponteiro para os dados de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="8da2c-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="8da2c-115">A memória alocada para *data* não deve ser liberada até que os dados da coluna sejam substituídos por outra chamada para **srv_setcoldata**, ou até que **srv_senddone** seja chamado.</span><span class="sxs-lookup"><span data-stu-id="8da2c-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8da2c-116">Retornos</span><span class="sxs-lookup"><span data-stu-id="8da2c-116">Returns</span></span>  
 <span data-ttu-id="8da2c-117">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="8da2c-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8da2c-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="8da2c-118">Remarks</span></span>  
 <span data-ttu-id="8da2c-119">Cada coluna da linha deve ser definida primeiro com **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="8da2c-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="8da2c-120">Os endereços dos dados da coluna são definidos inicialmente com **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="8da2c-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="8da2c-121">Se o endereço dos dados da coluna for alterado, **srv_setcoldata** deverá ser chamado para especificar o novo endereço e **srv_setcoldata** deverá ser chamado separadamente para cada coluna alterada.</span><span class="sxs-lookup"><span data-stu-id="8da2c-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="8da2c-122">Os dados nulos são representados definindo-se o comprimento da coluna como 0 com **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="8da2c-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="8da2c-123">Portanto, o endereço dos dados é ignorado.</span><span class="sxs-lookup"><span data-stu-id="8da2c-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8da2c-124">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="8da2c-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="8da2c-125">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="8da2c-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da2c-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8da2c-126">See Also</span></span>  
 [<span data-ttu-id="8da2c-127">srv_describe &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="8da2c-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
