---
title: Método SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683996"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ac17e-102">Método SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ac17e-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ac17e-103">O método SetExtendedProtectionSettings é usado para definir as propriedades RSWindowsExtendedProtectionLevel e RSWindowsExtendedProtectionScenario no arquivo de configuração RSReportServer.config do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac17e-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac17e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ac17e-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac17e-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="ac17e-105">Parameters</span></span>  
 <span data-ttu-id="ac17e-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="ac17e-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="ac17e-107">Define o RSWindowsExtendedProtectionLevel no arquivo RSRreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ac17e-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="ac17e-108">O valor obrigatório não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ac17e-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="ac17e-109">A lista a seguir mostra os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="ac17e-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="ac17e-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="ac17e-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="ac17e-111">Define o RSWindowsExtendedProtectionScenario no arquivo RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ac17e-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="ac17e-112">O valor obrigatório não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ac17e-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="ac17e-113">A lista a seguir mostra os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="ac17e-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="ac17e-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="ac17e-114">Remarks</span></span>  
 <span data-ttu-id="ac17e-115">As propriedades RSWindowsExtendedProtectionLevel e RSWindowsExtendedProtectionScenario aplicam-se quando AuthenticationTypes no arquivo RSReportServer.config inclui RSWindowNTLM, RSWindowsNegotiate ou RSWindowsKerberos.</span><span class="sxs-lookup"><span data-stu-id="ac17e-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="ac17e-116">Definir essas propriedades afeta a maneira como os usuários e o software cliente se autenticam com um servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ac17e-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="ac17e-117">É recomendável ler a documentação da proteção estendida antes de definir ExtendedProtectionLevel como `Allow` ou `Require`.</span><span class="sxs-lookup"><span data-stu-id="ac17e-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="ac17e-118">Para definir o ExtendedProtectionLevel, o usuário deve ser membro do grupo BUILTIN\Administradores no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ac17e-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac17e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac17e-119">Requirements</span></span>  
 <span data-ttu-id="ac17e-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac17e-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac17e-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ac17e-121">See Also</span></span>  
 <span data-ttu-id="ac17e-122">[Propriedade RSWindowsExtendedProtectionScenario &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="ac17e-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="ac17e-123">[Propriedade RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="ac17e-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="ac17e-124">[Proteção Estendida para Autenticação com o Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ac17e-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="ac17e-125">Arquivo de configuração RSReportServer</span><span class="sxs-lookup"><span data-stu-id="ac17e-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
