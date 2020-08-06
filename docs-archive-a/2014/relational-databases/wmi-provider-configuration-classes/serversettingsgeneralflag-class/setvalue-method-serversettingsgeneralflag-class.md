---
title: Método SetValue (classe ServerSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686210"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="c2f35-102">Método SetValue (classe ServerSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="c2f35-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="c2f35-103">Define todos os valores do sinalizador referenciado.</span><span class="sxs-lookup"><span data-stu-id="c2f35-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2f35-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c2f35-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c2f35-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c2f35-105">Parts</span></span>  
 <span data-ttu-id="c2f35-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c2f35-106">*object*</span></span>  
 <span data-ttu-id="c2f35-107">Um objeto da [classe ServerSettingsGeneralFlag](serversettingsgeneralflag-class.md) que representa um sinalizador geral para as configurações de servidor.</span><span class="sxs-lookup"><span data-stu-id="c2f35-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c2f35-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c2f35-108">Parameters</span></span>  
  
|<span data-ttu-id="c2f35-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="c2f35-109">Parameter</span></span>|<span data-ttu-id="c2f35-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="c2f35-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2f35-111">*Valor*</span><span class="sxs-lookup"><span data-stu-id="c2f35-111">*Value*</span></span>|<span data-ttu-id="c2f35-112">Um valor booliano que especifica o valor do sinalizador.</span><span class="sxs-lookup"><span data-stu-id="c2f35-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c2f35-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="c2f35-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="c2f35-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="c2f35-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2f35-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="c2f35-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f35-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2f35-116">See Also</span></span>  
 <span data-ttu-id="c2f35-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2f35-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
