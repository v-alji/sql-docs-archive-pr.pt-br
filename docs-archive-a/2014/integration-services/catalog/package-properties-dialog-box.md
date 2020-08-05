---
title: Caixa de diálogo Propriedades do Pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572645"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="571be-102">Caixa de diálogo Propriedades do Pacote</span><span class="sxs-lookup"><span data-stu-id="571be-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="571be-103">Use a caixa de diálogo **Propriedades do Pacote** para exibir propriedades de pacotes individuais armazenados no servidor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="571be-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="571be-104">Para obter mais informações, consulte [Servidor do Integration Services &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="571be-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="571be-105">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="571be-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="571be-106">Abrir a caixa de diálogo Propriedades do Pacote</span><span class="sxs-lookup"><span data-stu-id="571be-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="571be-107">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="571be-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="571be-108">Abrir a caixa de diálogo Propriedades do Pacote</span><span class="sxs-lookup"><span data-stu-id="571be-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="571be-109">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="571be-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="571be-110">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="571be-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="571be-111">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="571be-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="571be-112">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="571be-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="571be-113">Expanda a pasta que contém o pacote para o qual você deseja exibir propriedades.</span><span class="sxs-lookup"><span data-stu-id="571be-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="571be-114">Clique com o botão direito do mouse no pacote e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="571be-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="571be-115">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="571be-115">Configure the Options</span></span>  
 <span data-ttu-id="571be-116">Use a página **Geral** para exibir as propriedades do pacote selecionado.</span><span class="sxs-lookup"><span data-stu-id="571be-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="571be-117">Todas as propriedades da página **Geral** são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="571be-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="571be-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="571be-118">**Name**</span></span>  
 <span data-ttu-id="571be-119">Exibe o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="571be-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="571be-120">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="571be-120">**Identifier**</span></span>  
 <span data-ttu-id="571be-121">Lista a ID do pacote.</span><span class="sxs-lookup"><span data-stu-id="571be-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="571be-122">**Entry Point**</span><span class="sxs-lookup"><span data-stu-id="571be-122">**Entry Point**</span></span>  
 <span data-ttu-id="571be-123">O valor de `True` indica que o pacote é iniciado diretamente.</span><span class="sxs-lookup"><span data-stu-id="571be-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="571be-124">O valor de `False` indica que o pacote é iniciado por outro pacote usando a tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="571be-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="571be-125">O valor padrão é `True`.</span><span class="sxs-lookup"><span data-stu-id="571be-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="571be-126">Defina essa propriedade no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para o pacote pai e os pacotes filho clicando com o botão direito do mouse no pacote em Gerenciador de Soluções e clicando em **Pacote de Ponto de Entrada**.</span><span class="sxs-lookup"><span data-stu-id="571be-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="571be-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="571be-127">**Description**</span></span>  
 <span data-ttu-id="571be-128">Exibe a descrição opcional do pacote.</span><span class="sxs-lookup"><span data-stu-id="571be-128">Displays the optional description of the package.</span></span>  
  
  
