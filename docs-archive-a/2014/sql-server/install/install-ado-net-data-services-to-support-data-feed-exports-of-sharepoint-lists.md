---
title: Instalar o ADO.NET Data Services para dar suporte a exportações de feed de dados de listas do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571775"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="36817-102">Instalar o ADO.NET Data Services para dar suporte a exportações do feed de dados das listas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="36817-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="36817-103">O ADO.NET Data Services é obrigatório para uma exportação do feed de dados das listas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36817-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="36817-104">Como o SharePoint 2010 não inclui esse componente no programa SharePoint Prerequisite Installer, você deve instalá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="36817-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="36817-105">Sem esse pré-requisito, você obterá o erro a seguir ao tentar usar uma lista do SharePoint exportada como um feed de dados: "por razões de segurança, o DTD é proibido neste documento XML.</span><span class="sxs-lookup"><span data-stu-id="36817-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="36817-106">Para habilitar o processamento do DTD, defina a propriedade ProhibitDtd em XmlReaderSettings como falsa e passe as configurações para o método XmlReader.Create."</span><span class="sxs-lookup"><span data-stu-id="36817-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="36817-107">Use as instruções a seguir para instalar o ADO.NET Data Services em cada SharePoint Server para o qual você deseja permitir a exportação de listas como feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="36817-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="36817-108">Baixar e instalar o ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="36817-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="36817-109">Acesse a documentação de requisitos de hardware e software para o SharePoint 2010, [requisitos de hardware e software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span><span class="sxs-lookup"><span data-stu-id="36817-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="36817-110">Em **acesso ao software aplicável**, encontre o link para o ADO.NET Data Services 3,5 que corresponde ao sistema operacional que você está usando (windows Server 2008 SP2 ou windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="36817-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="36817-111">Clique no link e execute o programa de instalação que instala o serviço.</span><span class="sxs-lookup"><span data-stu-id="36817-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36817-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36817-112">See Also</span></span>  
 [<span data-ttu-id="36817-113">Instalação do PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="36817-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
