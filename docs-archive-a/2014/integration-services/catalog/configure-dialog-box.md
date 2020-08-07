---
title: Caixa de diálogo Configurar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575293"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="fb6ed-102">Caixa de diálogo Configurar</span><span class="sxs-lookup"><span data-stu-id="fb6ed-102">Configure Dialog Box</span></span>
  <span data-ttu-id="fb6ed-103">Use a caixa de diálogo **Configurar** para configurar parâmetros, gerenciadores de conexões e referências a ambientes para projetos e pacotes.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="fb6ed-104">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="fb6ed-105">Abrir a caixa de diálogo Configurar</span><span class="sxs-lookup"><span data-stu-id="fb6ed-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="fb6ed-106">Definir as opções na página Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fb6ed-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="fb6ed-107">Definir as opções na página Referências</span><span class="sxs-lookup"><span data-stu-id="fb6ed-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="fb6ed-108">Abrir a caixa de diálogo Configurar</span><span class="sxs-lookup"><span data-stu-id="fb6ed-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="fb6ed-109">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="fb6ed-110">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="fb6ed-111">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="fb6ed-112">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="fb6ed-113">Expanda a pasta que contém o pacote ou projeto que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="fb6ed-114">Clique com o botão direito do mouse no pacote ou projeto e clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="fb6ed-115">Definir as opções na página Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fb6ed-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="fb6ed-116">Use a página **Parâmetros** para exibir nomes e valores de parâmetro, e para modificar os valores.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="fb6ed-117">Selecione o escopo dos parâmetros exibidos nas guias **Parâmetros** e **Gerenciadores de Conexões** , na lista suspensa **Escopo** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="fb6ed-118">Esta é uma lista das opções na guia **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="fb6ed-119">**Contêiner**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-119">**Container**</span></span>  
 <span data-ttu-id="fb6ed-120">Lista o objeto que contém o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="fb6ed-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-121">**Name**</span></span>  
 <span data-ttu-id="fb6ed-122">Lista o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="fb6ed-123">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-123">**Value**</span></span>  
 <span data-ttu-id="fb6ed-124">Lista o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-124">Lists the parameter value.</span></span> <span data-ttu-id="fb6ed-125">Clique no botão de reticências para alterar o valor na caixa de diálogo **Definir Valor do Parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="fb6ed-126">Esta é uma lista das opções na guia **Gerenciadores de Conexões** . Use essa guia para alterar valores de propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="fb6ed-127">Os parâmetros são gerados automaticamente no servidor do SSIS para as propriedades.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="fb6ed-128">**Contêiner**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-128">**Container**</span></span>  
 <span data-ttu-id="fb6ed-129">Lista o objeto que contém o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="fb6ed-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-130">**Name**</span></span>  
 <span data-ttu-id="fb6ed-131">Lista o nome do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="fb6ed-132">**Nome da propriedade**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-132">**Property name**</span></span>  
 <span data-ttu-id="fb6ed-133">Lista o nome da propriedade do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="fb6ed-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-134">**Value**</span></span>  
 <span data-ttu-id="fb6ed-135">Lista o valor atribuído à propriedade do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="fb6ed-136">Clique no botão de reticências para alterar o valor na caixa de diálogo **Definir Valor do Parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="fb6ed-137">Você pode inserir um valor literal, mapear uma variável de ambiente que contém o valor a ser usado, ou usar o valor padrão do pacote.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="fb6ed-138">Definir as opções na página Referências</span><span class="sxs-lookup"><span data-stu-id="fb6ed-138">Set the options on the References page</span></span>  
 <span data-ttu-id="fb6ed-139">Use a página **Referências** para adicionar e remover referências a ambientes, e para acessar propriedades de ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="fb6ed-140">Um ambiente especificar valores de runtime para pacotes contidos nos projetos que você implantou no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb6ed-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="fb6ed-141">**Ambiente**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-141">**Environment**</span></span>  
 <span data-ttu-id="fb6ed-142">Lista o ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="fb6ed-143">**Pasta de Ambiente**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-143">**Environment Folder**</span></span>  
 <span data-ttu-id="fb6ed-144">Lista a pasta que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="fb6ed-145">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-145">**Open**</span></span>  
 <span data-ttu-id="fb6ed-146">Clique para abrir a caixa de diálogo **Propriedades do Ambiente** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="fb6ed-147">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-147">**Add**</span></span>  
 <span data-ttu-id="fb6ed-148">Clique para adicionar uma referência a um ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="fb6ed-149">Na caixa de diálogo **Procurar Ambientes** , clique em um ambiente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="fb6ed-150">Você pode selecionar um ambiente contido em qualquer pasta de projeto no nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="fb6ed-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="fb6ed-151">**Remover**</span><span class="sxs-lookup"><span data-stu-id="fb6ed-151">**Remove**</span></span>  
 <span data-ttu-id="fb6ed-152">Clique em um ambiente listado na área **Referências** e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="fb6ed-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
