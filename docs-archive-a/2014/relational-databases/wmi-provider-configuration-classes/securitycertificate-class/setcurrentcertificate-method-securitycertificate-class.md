---
title: Método SetCurrentCertificate (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571905"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="43bad-102">Método SetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="43bad-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="43bad-103">Define o certificado de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="43bad-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43bad-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="43bad-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="43bad-105">Partes</span><span class="sxs-lookup"><span data-stu-id="43bad-105">Parts</span></span>  
 <span data-ttu-id="43bad-106">*object*</span><span class="sxs-lookup"><span data-stu-id="43bad-106">*object*</span></span>  
 <span data-ttu-id="43bad-107">Um objeto [SecurityCertificate Class] SecurityCertificate-class.md) que representa um certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="43bad-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="43bad-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="43bad-108">Parameters</span></span>  
  
|<span data-ttu-id="43bad-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="43bad-109">Parameter</span></span>|<span data-ttu-id="43bad-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="43bad-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43bad-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="43bad-111">*SHA*</span></span>|<span data-ttu-id="43bad-112">Um valor da cadeia de caracteres que especifica a impressão digital de SHA (algoritmo de hash seguro) para o certificado de segurança necessário.</span><span class="sxs-lookup"><span data-stu-id="43bad-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="43bad-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="43bad-113">*SQLInstance*</span></span>|<span data-ttu-id="43bad-114">Um valor da cadeia de caracteres que especifica a instância para a qual o certificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="43bad-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="43bad-115">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="43bad-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="43bad-116">Um valor uint32, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="43bad-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43bad-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="43bad-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bad-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43bad-118">See Also</span></span>  
 <span data-ttu-id="43bad-119">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="43bad-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
