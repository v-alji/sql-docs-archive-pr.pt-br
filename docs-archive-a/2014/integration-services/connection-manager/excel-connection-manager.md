---
title: Gerenciador de conexões do Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573243"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="0e0a8-102">Gerenciador de conexões do Excel</span><span class="sxs-lookup"><span data-stu-id="0e0a8-102">Excel Connection Manager</span></span>
  <span data-ttu-id="0e0a8-103">Um gerenciador de conexão do Excel permite a conexão de um pacote a um arquivo de pasta de trabalho do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel existente.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="0e0a8-104">A origem do Excel e o destino do Excel que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluem usar o Gerenciador de conexões do Excel.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="0e0a8-105">Quando você adiciona um gerenciador de conexões do Excel a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que é resolvido como uma conexão do Excel em tempo de execução, define as propriedades do gerenciador de conexões e o adiciona à coleção `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="0e0a8-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `EXCEL`.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e0a8-107">Não é possível estabelecer conexão com um arquivo do Excel protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="0e0a8-108">Configuração do gerenciador de conexões do Excel</span><span class="sxs-lookup"><span data-stu-id="0e0a8-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="0e0a8-109">Você pode configurar o gerenciador de conexões do Excel dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="0e0a8-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="0e0a8-110">Especificando o caminho do arquivo de pasta de trabalho Excel.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="0e0a8-111">Especificando a versão do Excel que foi usada para criar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="0e0a8-112">Indicando se a primeira linha de dados acessados nas planilhas ou intervalos selecionados contém nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="0e0a8-113">Se o gerenciador de conexões do Excel for usado por uma origem do Excel, os nomes das colunas serão incluídos junto com os dados extraídos.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="0e0a8-114">Se for usado por um destino do Excel, os nomes das colunas serão incluídos nos dados gravados.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="0e0a8-115">O gerenciador de conexões do Excel usa o [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 e o driver de método de acesso sequencial indexado (ISAM) do Excel para se conectar, ler e gravar dados nas fontes de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="0e0a8-116">Para obter mais informações sobre o comportamento desse provedor e driver quando usado com fontes do Excel e destinos do Excel, consulte [origem do Excel](../data-flow/excel-source.md) e [destino do Excel](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="0e0a8-117">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0e0a8-118">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor do Gerenciador de Conexões do Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="0e0a8-119">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="0e0a8-120">Para obter informações sobre loop através de um grupo de arquivos do Excel, consulte [Loop por meio de arquivos do Excel e tabelas usando um contêiner de Loop Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0e0a8-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0e0a8-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0e0a8-122">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="0e0a8-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="0e0a8-123">Importar dados do Excel ou exportar dados para o Excel com o SSIS (SQL Server Integration Services)</span><span class="sxs-lookup"><span data-stu-id="0e0a8-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
