---
title: srv_setutype (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684748"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="aa819-102">srv_setutype (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="aa819-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="aa819-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="aa819-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="aa819-104">Define o tipo de dados definido pelo usuário para uma coluna em uma linha.</span><span class="sxs-lookup"><span data-stu-id="aa819-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa819-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa819-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="aa819-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aa819-106">Arguments</span></span>  
 <span data-ttu-id="aa819-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="aa819-107">*srvproc*</span></span>  
 <span data-ttu-id="aa819-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="aa819-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="aa819-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="aa819-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="aa819-110">*column*</span><span class="sxs-lookup"><span data-stu-id="aa819-110">*column*</span></span>  
 <span data-ttu-id="aa819-111">Indica qual coluna deve ser definida.</span><span class="sxs-lookup"><span data-stu-id="aa819-111">Indicates which column to set.</span></span> <span data-ttu-id="aa819-112">As colunas são numeradas a partir de 1.</span><span class="sxs-lookup"><span data-stu-id="aa819-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="aa819-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="aa819-113">*user_type*</span></span>  
 <span data-ttu-id="aa819-114">Especifica o código do tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="aa819-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="aa819-115">Retornos</span><span class="sxs-lookup"><span data-stu-id="aa819-115">Returns</span></span>  
 <span data-ttu-id="aa819-116">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="aa819-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="aa819-117">Retornará FAIL se a coluna não existir.</span><span class="sxs-lookup"><span data-stu-id="aa819-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa819-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa819-118">Remarks</span></span>  
 <span data-ttu-id="aa819-119">Uma coluna tem dois tipos de dados: seu tipo de dados real e seu tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="aa819-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="aa819-120">O tipo de dados definido pelo usuário é usado pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para armazenar o tipo de dados real definido pelo usuário da coluna, se houver, e informações de descrição de coluna, como a nulidade e a capacidade de atualização, para a coluna.</span><span class="sxs-lookup"><span data-stu-id="aa819-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="aa819-121">A função **srv_setutype** pode ser chamada a qualquer momento em que *column* tenha sido definido com **srv_describe** e antes que a última linha tenha sido enviada.</span><span class="sxs-lookup"><span data-stu-id="aa819-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa819-122">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="aa819-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="aa819-123">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="aa819-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa819-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa819-124">See Also</span></span>  
 [<span data-ttu-id="aa819-125">srv_describe &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="aa819-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
