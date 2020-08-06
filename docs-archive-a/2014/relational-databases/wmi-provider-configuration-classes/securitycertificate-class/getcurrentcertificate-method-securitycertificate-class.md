---
title: Método GetCurrentCertificate (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679254"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="c33be-102">Método GetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="c33be-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="c33be-103">Obtém o certificado de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="c33be-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33be-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c33be-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c33be-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c33be-105">Parts</span></span>  
 <span data-ttu-id="c33be-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c33be-106">*object*</span></span>  
 <span data-ttu-id="c33be-107">Um objeto da [classe SecurityCertificate](securitycertificate-class.md) que representa um certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="c33be-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c33be-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c33be-108">Parameters</span></span>  
  
|<span data-ttu-id="c33be-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="c33be-109">Parameter</span></span>|<span data-ttu-id="c33be-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="c33be-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c33be-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="c33be-111">*SHA*</span></span>|<span data-ttu-id="c33be-112">Um valor de objeto da cadeia de caracteres (parâmetro de saída) que especifica a impressão digital SHA do certificado de segurança atual depois que o método é concluído.</span><span class="sxs-lookup"><span data-stu-id="c33be-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="c33be-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="c33be-113">*SQLInstance*</span></span>|<span data-ttu-id="c33be-114">Um valor da cadeia de caracteres que especifica a instância para a qual o certificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="c33be-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c33be-115">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="c33be-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="c33be-116">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="c33be-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c33be-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="c33be-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33be-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c33be-118">See Also</span></span>  
 <span data-ttu-id="c33be-119">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c33be-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
