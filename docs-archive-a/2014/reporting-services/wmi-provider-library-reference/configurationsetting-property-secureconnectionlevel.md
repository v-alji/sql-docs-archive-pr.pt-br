---
title: Propriedade SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683964"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="16812-102">Propriedade SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="16812-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="16812-103">Retorna o nível de conexão segura especificado no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="16812-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="16812-104">Somente leitura.</span><span class="sxs-lookup"><span data-stu-id="16812-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16812-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="16812-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="16812-106">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="16812-106">Property Values</span></span>  
 <span data-ttu-id="16812-107">Um `Integer` valor que representa o nível de conexão segura.</span><span class="sxs-lookup"><span data-stu-id="16812-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="16812-108">Os valores de retorno indicam se o SSL está configurado ou não.</span><span class="sxs-lookup"><span data-stu-id="16812-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="16812-109">Um valor maior ou igual a 1 indica que o SSL está ativado.</span><span class="sxs-lookup"><span data-stu-id="16812-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="16812-110">Um valor de 0 indica que o SSL está desativado.</span><span class="sxs-lookup"><span data-stu-id="16812-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="16812-111">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="16812-111">Example Code</span></span>  
 [<span data-ttu-id="16812-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="16812-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="16812-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16812-113">Requirements</span></span>  
 <span data-ttu-id="16812-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16812-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16812-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16812-115">See Also</span></span>  
 [<span data-ttu-id="16812-116">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="16812-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
