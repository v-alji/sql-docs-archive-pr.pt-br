---
title: Método SetServiceAccount (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679212"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="f5c8d-102">Método SetServiceAccount (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="f5c8d-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="f5c8d-103">Tenta alterar o nome de usuário e senha com os quais o serviço é executado.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c8d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5c8d-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f5c8d-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f5c8d-105">Parts</span></span>  
 <span data-ttu-id="f5c8d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-106">*object*</span></span>  
 <span data-ttu-id="f5c8d-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="f5c8d-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f5c8d-108">Parameters</span></span>  
 <span data-ttu-id="f5c8d-109">*Instart*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="f5c8d-110">Um valor da cadeia de caracteres que especifica o nome de conta com a qual o serviço é executado.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="f5c8d-111">Dependendo do tipo de serviço, o nome da conta pode estar no formulário de DomainName\Username.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="f5c8d-112">Quando for executado, o processo de serviço será registrado usando-se um dos dois formulários:</span><span class="sxs-lookup"><span data-stu-id="f5c8d-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="f5c8d-113">Se a conta pertencer ao domínio interno, \Username poderá ser especificado.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="f5c8d-114">Se NULL for especificado, o serviço será conectado como a conta **LocalSystem** .</span><span class="sxs-lookup"><span data-stu-id="f5c8d-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="f5c8d-115">Para drivers de nível de kernel ou de sistema, o *StartName* contém o nome do objeto de driver, \FileSystem\Rdr ou \Driver\Xns, que o sistema de e/s usa para carregar o driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="f5c8d-116">Se NULL for especificado, o driver será executado com o nome do objeto padrão criado pelo sistema de E/S com base no nome do serviço, por exemplo DWDOM\Admin.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="f5c8d-117">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="f5c8d-118">Um valor de cadeia de caracteres que especifica a senha para o nome da conta no parâmetro *StartName* .</span><span class="sxs-lookup"><span data-stu-id="f5c8d-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="f5c8d-119">Especifique NULL se você não estiver alterando a senha.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="f5c8d-120">Especifique uma cadeia de caracteres vazia se o serviço não tiver nenhuma senha.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f5c8d-121">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="f5c8d-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="f5c8d-122">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito ou 1 se a solicitação não tiver suporte.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="f5c8d-123">Qualquer outro número indica um erro.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5c8d-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5c8d-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c8d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5c8d-125">See Also</span></span>  
 <span data-ttu-id="f5c8d-126">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f5c8d-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
