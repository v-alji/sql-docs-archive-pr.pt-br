---
title: Método SetCurrentCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 7349fb87-b973-4160-a2be-cab73abf5b31
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 44e65ab30659cacca09e63a94a1f3596a182dda5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679233"
---
# <a name="setcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="7c6a1-102">Método SetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="7c6a1-102">SetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="7c6a1-103">Define o certificado de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="7c6a1-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6a1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7c6a1-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7c6a1-105">Partes</span><span class="sxs-lookup"><span data-stu-id="7c6a1-105">Parts</span></span>  
 <span data-ttu-id="7c6a1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7c6a1-106">*object*</span></span>  
 <span data-ttu-id="7c6a1-107">Um objeto da [classe SInstance](sinstance-class.md) que representa as configurações de servidor em uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c6a1-107">An [SInstance Class](sinstance-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7c6a1-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7c6a1-108">Parameters</span></span>  
  
|<span data-ttu-id="7c6a1-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="7c6a1-109">Parameter</span></span>|<span data-ttu-id="7c6a1-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c6a1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c6a1-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="7c6a1-111">*SHA*</span></span>|<span data-ttu-id="7c6a1-112">Um valor da cadeia de caracteres que especifica o certificado de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="7c6a1-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7c6a1-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="7c6a1-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="7c6a1-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="7c6a1-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c6a1-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="7c6a1-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6a1-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c6a1-116">See Also</span></span>  
 <span data-ttu-id="7c6a1-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7c6a1-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
