---
title: Localizar a versão do esquema de definição de relatório (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680814"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="7a504-102">Localizar a versão do esquema de definição de relatório (SSRS)</span><span class="sxs-lookup"><span data-stu-id="7a504-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="7a504-103">Um arquivo de definição de relatório especifica o namespace do RDL para a versão do esquema de definição de relatório usado para validar o arquivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="7a504-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="7a504-104">Ao abrir um arquivo .rdl no ambiente de criação de relatório como o Designer de Relatórios do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou Construtor de Relatórios, se o relatório tiver sido criado para um namespace anterior, um arquivo de backup será criado automaticamente e o relatório será atualizado para o namespace atual.</span><span class="sxs-lookup"><span data-stu-id="7a504-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="7a504-105">Se você salvar a definição de relatório atualizada, terá salvo o arquivo .rdl convertido.</span><span class="sxs-lookup"><span data-stu-id="7a504-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="7a504-106">Esse é o único modo para atualizar uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="7a504-107">A própria definição de relatório não é atualizada em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="7a504-108">O relatório compilado é atualizado em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="7a504-109">Para obter mais informações, consulte [Upgrade Reports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7a504-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="7a504-110">Como identificar a versão do esquema RDL de um relatório</span><span class="sxs-lookup"><span data-stu-id="7a504-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="7a504-111">Abra o arquivo de relatório .rdl em um aplicativo como o Bloco de Notas ou Bloco de Notas XML 2007, que permite visualizar o xml.</span><span class="sxs-lookup"><span data-stu-id="7a504-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="7a504-112">O elemento Relatório XML especifica o namespace do esquema.</span><span class="sxs-lookup"><span data-stu-id="7a504-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="7a504-113">Por exemplo, o elemento Relatório a seguir especifica o namespace do Designer de Relatórios e o namespace da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="7a504-114">O namespace de definição de relatório é especificado pela seguinte URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="7a504-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="7a504-115">Como identificar a versão do esquema RDL de um Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="7a504-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="7a504-116">Abrir um novo projeto.</span><span class="sxs-lookup"><span data-stu-id="7a504-116">Open a new project.</span></span> <span data-ttu-id="7a504-117">A versão do projeto que você escolhe determina a versão do esquema RDL.</span><span class="sxs-lookup"><span data-stu-id="7a504-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="7a504-118">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], há suporte para mais de uma versão de esquema.</span><span class="sxs-lookup"><span data-stu-id="7a504-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="7a504-119">Para obter mais informações, veja [Implantação e suporte de versão no SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7a504-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="7a504-120">No menu **Projeto** , clique em **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="7a504-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7a504-121">A caixa de diálogo **Adicionar Novo Item** é aberta.</span><span class="sxs-lookup"><span data-stu-id="7a504-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7a504-122">No painel **Modelos** , clique em **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="7a504-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="7a504-123">Em **Nome**, digite um nome para o relatório ou aceite o padrão.</span><span class="sxs-lookup"><span data-stu-id="7a504-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="7a504-124">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a504-124">Click **Add**.</span></span> <span data-ttu-id="7a504-125">O Designer de Relatórios abre um novo relatório em branco na exibição Design.</span><span class="sxs-lookup"><span data-stu-id="7a504-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="7a504-126">No menu **Exibir** , clique em **Código**.</span><span class="sxs-lookup"><span data-stu-id="7a504-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="7a504-127">A definição de relatório é exibida como um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="7a504-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="7a504-128">O elemento Relatório XML especifica o namespace do esquema.</span><span class="sxs-lookup"><span data-stu-id="7a504-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="7a504-129">Por exemplo, o elemento Relatório a seguir especifica o namespace do Designer de Relatórios e o namespace da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="7a504-130">O namespace de definição de relatório é especificado pela seguinte URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="7a504-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="7a504-131">Como identificar a versão do esquema RDL no Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="7a504-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="7a504-132">No Gerenciador de Relatórios, digite a URL para o servidor de relatório:</span><span class="sxs-lookup"><span data-stu-id="7a504-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="7a504-133">Por exemplo, a URL a seguir especifica um servidor de relatório no computador local:</span><span class="sxs-lookup"><span data-stu-id="7a504-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="7a504-134">O arquivo .xsd é aberto no navegador.</span><span class="sxs-lookup"><span data-stu-id="7a504-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="7a504-135">O elemento de Esquema XML especifica o namespace do esquema.</span><span class="sxs-lookup"><span data-stu-id="7a504-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="7a504-136">Por exemplo, o elemento de esquema a seguir especifica três namespaces: a referência targetNamespace que é usada internamente pelo [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], a referência xsd do próprio esquema (xsd) e a referência de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="7a504-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="7a504-137">O namespace de definição de relatório é especificado pela seguinte URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="7a504-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a504-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a504-138">See Also</span></span>  
 <span data-ttu-id="7a504-139">[Atualizar relatórios](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="7a504-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="7a504-140">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7a504-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
