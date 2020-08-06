---
title: Método RemoveCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 7e5dbafa-a634-4617-9622-510514fce0ce
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4b876cd75778d1da9c9a46f65f39b915ebee0552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679232"
---
# <a name="removecertificate-method-sinstance-class"></a><span data-ttu-id="31d9f-102">Método RemoveCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="31d9f-102">RemoveCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="31d9f-103">Remove o certificado de segurança atual da instância de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31d9f-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d9f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="31d9f-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="31d9f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="31d9f-105">Parts</span></span>  
 <span data-ttu-id="31d9f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="31d9f-106">*object*</span></span>  
 <span data-ttu-id="31d9f-107">Um objeto da [classe SInstance](sinstance-class.md) que representa as configurações de servidor em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31d9f-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="31d9f-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="31d9f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="31d9f-109">Um valor uint32, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="31d9f-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31d9f-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="31d9f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d9f-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31d9f-111">See Also</span></span>  
 <span data-ttu-id="31d9f-112">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="31d9f-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
