---
title: Referência da biblioteca do provedor WMI do Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572894"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="77d5d-102">Referência da Biblioteca do provedor WMI do Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="77d5d-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="77d5d-103">O provedor WMI (Instrumentação de Gerenciamento do Windows) do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dá suporte às operações do WMI que permitem gravar scripts e código para modificar as configurações do servidor de relatório e do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="77d5d-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="77d5d-104">Por exemplo, se você quiser alterar quando a segurança integrada é usada quando o servidor de relatório se conecta ao banco de dados do servidor de relatório, crie uma instância da classe MSReportServer_ConfigurationSetting e use a propriedade DatabaseIntegratedSecurity da instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="77d5d-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="77d5d-105">As classes mostradas na tabela a seguir representam os componentes do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77d5d-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="77d5d-106">As classes são definidas nos namespaces do [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] ou do [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77d5d-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="77d5d-107">Cada uma das classes oferece suporte às operações de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="77d5d-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="77d5d-108">As operações de criação não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="77d5d-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="77d5d-109">Classes</span><span class="sxs-lookup"><span data-stu-id="77d5d-109">Classes</span></span>  
 [<span data-ttu-id="77d5d-110">Classe MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="77d5d-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="77d5d-111">Fornece as informações básicas exigidas para um cliente se conectar a um servidor de relatório instalado.</span><span class="sxs-lookup"><span data-stu-id="77d5d-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="77d5d-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="77d5d-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="77d5d-113">Representa os parâmetros de instalação e de tempo de execução de uma instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="77d5d-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="77d5d-114">Esses parâmetros são armazenados no arquivo de configuração para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="77d5d-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="77d5d-115">Para obter mais informações sobre as operações do WMI, consulte a documentação do SDK do WMI incluída no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="77d5d-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d5d-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77d5d-116">See Also</span></span>  
 <span data-ttu-id="77d5d-117">[Acessar o provedor WMI de Reporting Services](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="77d5d-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="77d5d-118">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="77d5d-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
