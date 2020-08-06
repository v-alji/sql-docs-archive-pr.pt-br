---
title: Método SetDefaults (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680332"
---
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="175d9-102">Método SetDefaults (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="175d9-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="175d9-103">Define todos os valores padrão para a instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com a opção de substituir os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="175d9-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="175d9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="175d9-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="175d9-105">Partes</span><span class="sxs-lookup"><span data-stu-id="175d9-105">Parts</span></span>  
 <span data-ttu-id="175d9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="175d9-106">*object*</span></span>  
 <span data-ttu-id="175d9-107">Um objeto de [classe ServerSettings](serversettings-class.md) que representa uma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instância de cliente.</span><span class="sxs-lookup"><span data-stu-id="175d9-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="175d9-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="175d9-108">Parameters</span></span>  
  
|<span data-ttu-id="175d9-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="175d9-109">Parameter</span></span>|<span data-ttu-id="175d9-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="175d9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="175d9-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="175d9-111">*OverwriteAll*</span></span>|<span data-ttu-id="175d9-112">Um valor booliano, que especifica se deve-se substituir valores existentes na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` para substituir dados existentes, ou `false`, se os dados existentes não precisarem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="175d9-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="175d9-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="175d9-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="175d9-114">Um valor u`int32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="175d9-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="175d9-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="175d9-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175d9-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="175d9-116">See Also</span></span>  
 <span data-ttu-id="175d9-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="175d9-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
