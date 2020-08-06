---
title: Implantando uma extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685448"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="bf123-102">Implantando uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="bf123-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="bf123-103">Depois de gravar e compilar a extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] em uma biblioteca do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], você precisa torná-la detectável pelo servidor de relatório e pelo Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="bf123-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="bf123-104">Isso é tão fácil quanto copiar a extensão para os diretórios adequados e adicionar entradas aos arquivos de configuração do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] adequados.</span><span class="sxs-lookup"><span data-stu-id="bf123-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="bf123-105">Elemento de extensão do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="bf123-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="bf123-106">As extensões de processamento de dados implantadas no servidor de relatório ou no Designer de Relatórios devem ser inseridas como elementos **Extension** nos arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="bf123-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="bf123-107">Esses arquivos são o RSReportServer.config para o servidor de relatório e o RSReportDesigner.config para Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="bf123-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="bf123-108">A tabela a seguir descreve os atributos do elemento **Extension** das extensões de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="bf123-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="bf123-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="bf123-109">Attribute</span></span>|<span data-ttu-id="bf123-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="bf123-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="bf123-111">Um nome exclusivo para a extensão, por exemplo, o "SQL" para a extensão de processamento de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou "OLEDB" para a extensão de processamento de dados OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bf123-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="bf123-112">O comprimento máximo do atributo `Name` é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="bf123-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="bf123-113">O nome deve ser exclusivo entre todas as entradas dento do elemento **Extension** de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="bf123-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="bf123-114">Uma lista separada por vírgulas que inclui o namespace totalmente qualificado junto com o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="bf123-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="bf123-115">Um valor `false` indica que a extensão de processamento de dados não deve ser visível nas interfaces do usuário.</span><span class="sxs-lookup"><span data-stu-id="bf123-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="bf123-116">Se o atributo não for incluído, o valor padrão será `true`.</span><span class="sxs-lookup"><span data-stu-id="bf123-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="bf123-117">Para obter mais informações sobre os arquivos RSReportServer.config ou RSReportDesigner.config, consulte [Arquivos de configuração do Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="bf123-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf123-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bf123-118">In This Section</span></span>  
  
|<span data-ttu-id="bf123-119">Tópico</span><span class="sxs-lookup"><span data-stu-id="bf123-119">Topic</span></span>|<span data-ttu-id="bf123-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf123-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bf123-121">Como fazer: Para implantar uma extensão de processamento de dados para um Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="bf123-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="bf123-122">Descreve como implantar sua extensão de processamento de dados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bf123-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="bf123-123">Como fazer: Para implantar uma extensão de processamento de dados para o Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="bf123-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="bf123-124">Descreve como implantar sua extensão de processamento de dados em um Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="bf123-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf123-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf123-125">See Also</span></span>  
 <span data-ttu-id="bf123-126">[Extensões de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="bf123-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="bf123-127">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="bf123-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="bf123-128">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bf123-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
