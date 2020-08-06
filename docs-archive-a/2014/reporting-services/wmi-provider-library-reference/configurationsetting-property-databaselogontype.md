---
title: Propriedade DatabaseLogonType (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683975"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ee6dc-102">Propriedade DatabaseLogonType (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ee6dc-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ee6dc-103">Especifica se o servidor de relatório usa uma conta de serviço do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, uma conta do usuário do Windows ou um logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para acessar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="ee6dc-104">Somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6dc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee6dc-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="ee6dc-106">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="ee6dc-106">Property Values</span></span>  
 <span data-ttu-id="ee6dc-107">Um objeto `integer` que representa o tipo de logon.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="ee6dc-108">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="ee6dc-108">Example Code</span></span>  
 [<span data-ttu-id="ee6dc-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ee6dc-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="ee6dc-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="ee6dc-110">Remarks</span></span>  
 <span data-ttu-id="ee6dc-111">Os valores são:</span><span class="sxs-lookup"><span data-stu-id="ee6dc-111">Values are:</span></span>  
  
-   <span data-ttu-id="ee6dc-112">0 para logon do Windows</span><span class="sxs-lookup"><span data-stu-id="ee6dc-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="ee6dc-113">1 para logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee6dc-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="ee6dc-114">2 para fazer logon como um serviço</span><span class="sxs-lookup"><span data-stu-id="ee6dc-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="ee6dc-115">Se você especificar 0 (Windows), deverá definir o valor na propriedade [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) com uma conta de usuário válida e correspondente do Windows.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="ee6dc-116">Se especificar 1 (SQL Server), certifique-se de que o valor de [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponda a um logon válido do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee6dc-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="ee6dc-117">Se você especificar 2 (serviço Windows), o servidor de relatório usará uma conta [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] e a conta de serviço do Windows para acessar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="ee6dc-118">A propriedade DatabaseLogonAccount é ignorada.</span><span class="sxs-lookup"><span data-stu-id="ee6dc-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6dc-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee6dc-119">Requirements</span></span>  
 <span data-ttu-id="ee6dc-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee6dc-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6dc-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee6dc-121">See Also</span></span>  
 [<span data-ttu-id="ee6dc-122">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ee6dc-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
