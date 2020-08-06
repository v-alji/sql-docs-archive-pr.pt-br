---
title: Gerar Scripts
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582965"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="0d226-102">Gerar scripts (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0d226-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0d226-103">fornece dois mecanismos para gerar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d226-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="0d226-104">Você pode criar scripts para vários objetos usando o **Assistente para gerar e publicar scripts.**</span><span class="sxs-lookup"><span data-stu-id="0d226-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="0d226-105">É possível gerar um script para objetos individuais ou para vários objetos usando o menu **Gerar script como** no **Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="0d226-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="0d226-106">**Escolha um método:**  [Assistente para Gerar e Publicar Scripts](#GenPubScriptWiz), [Menu Script Como do Pesquisador de Objetos](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="0d226-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="0d226-107">**Para usar o menu Script Como:**  [Gerar script de um único objeto](#ScriptSingleObject), [Gerar script de dois objetos usando o Pesquisador de Objetos](#ScriptTwoObjectsOE), [Gerar script de dois objetos usando detalhes do Pesquisador de Objetos](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="0d226-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0d226-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0d226-108">Before You Begin</span></span>  
 <span data-ttu-id="0d226-109">Escolha o mecanismo que melhor satisfaz seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="0d226-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="0d226-110">Assistente para Gerar e Publicar Scripts</span><span class="sxs-lookup"><span data-stu-id="0d226-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="0d226-111">Use o **Assistente para Gerar e Publicar Scripts** para criar um script [!INCLUDE[tsql](../../includes/tsql-md.md)] para vários objetos.</span><span class="sxs-lookup"><span data-stu-id="0d226-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="0d226-112">O assistente gera um script de todos os objetos de um banco de dados ou de um subconjunto dos objetos selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d226-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="0d226-113">O assistente tem muitas opções para seus scripts, por exemplo, se permissões, ordenações, restrições etc. devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="0d226-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="0d226-114">Para obter instruções sobre como usar o assistente, veja [Assistente para Gerar e Publicar Scripts](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0d226-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="0d226-115">Menu Script Como do Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="0d226-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="0d226-116">Você pode usar o menu **Gerar Script como do Pesquisador de Objetos** para gerar script de um único objeto, de vários objetos ou de várias instruções para um único objeto.</span><span class="sxs-lookup"><span data-stu-id="0d226-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="0d226-117">É possível escolher um de vários tipos de scripts. Por exemplo, para criar, alterar ou descartar o objeto.</span><span class="sxs-lookup"><span data-stu-id="0d226-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="0d226-118">É possível salvar o script em uma janela do Editor de Consultas em um arquivo ou na Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="0d226-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="0d226-119">O script é criado em formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="0d226-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="0d226-120">Para gerar um script de um único objeto</span><span class="sxs-lookup"><span data-stu-id="0d226-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="0d226-121">**Para gerar script de um único objeto**</span><span class="sxs-lookup"><span data-stu-id="0d226-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="0d226-122">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="0d226-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0d226-123">Expanda **Bancos de Dados**e o banco de dados que contém o objeto do qual será gerado um script.</span><span class="sxs-lookup"><span data-stu-id="0d226-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="0d226-124">Expanda a categoria do objeto.</span><span class="sxs-lookup"><span data-stu-id="0d226-124">Expand the category of the object.</span></span> <span data-ttu-id="0d226-125">Por exemplo, expanda o nó **Tabelas** ou **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="0d226-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="0d226-126">Clique com o botão direito do mouse no objeto, aponte para **script \<object type> como**, por exemplo, apontar para **script de tabela como**.</span><span class="sxs-lookup"><span data-stu-id="0d226-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="0d226-127">Aponte para o tipo de script, como **Criar para** ou **Alterar para**.</span><span class="sxs-lookup"><span data-stu-id="0d226-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="0d226-128">Selecione o local para salvar o script, como **Nova janela do Editor de Consultas** ou **Área de Transferência**.</span><span class="sxs-lookup"><span data-stu-id="0d226-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a> <span data-ttu-id="0d226-129">Para gerar um script de dois objetos usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="0d226-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="0d226-130">**Para gerar um script de dois objetos usando o Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="0d226-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="0d226-131">Talvez você queira um script que tenha várias opções, como descartar um procedimento e, em seguida, criar um procedimento ou criar uma tabela e alterá-la.</span><span class="sxs-lookup"><span data-stu-id="0d226-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="0d226-132">Os processos a seguir para gerar scripts de vários objetos também funcionarão se você precisar criar um script que faça referência a tipos de objetos diferentes, como tabelas, exibições e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="0d226-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="0d226-133">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="0d226-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0d226-134">Expanda **Bancos de Dados**e o banco de dados que contém os objetos dos quais será gerado um script.</span><span class="sxs-lookup"><span data-stu-id="0d226-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="0d226-135">Clique com o botão direito do mouse no primeiro objeto a ser inserido no script, aponte para **script \<object type> como**e, nas seleções **salvar como** , escolha **nova janela do editor de consultas** como o destino de saída.</span><span class="sxs-lookup"><span data-stu-id="0d226-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="0d226-136">Navegue até o segundo objeto do qual deseja gerar script.</span><span class="sxs-lookup"><span data-stu-id="0d226-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="0d226-137">Clique com o botão direito do mouse no objeto, aponte para **script \<object type> como**e, nas seleções **salvar como** , escolha **área de transferência** como o destino de saída.</span><span class="sxs-lookup"><span data-stu-id="0d226-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="0d226-138">Na janela Editor de Consultas aberta para o primeiro objeto, cole o script para o segundo objeto da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0d226-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a> <span data-ttu-id="0d226-139">Para gerar um script de dois objetos usando Detalhes do Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="0d226-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="0d226-140">**Para gerar um script de dois objetos usando Detalhes do Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="0d226-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="0d226-141">É possível usar o painel **Detalhes do Pesquisador de Objetos** para gerar um script para vários objetos da mesma categoria.</span><span class="sxs-lookup"><span data-stu-id="0d226-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="0d226-142">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="0d226-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0d226-143">Expanda **Bancos de Dados**e o banco de dados que contém os objetos dos quais será gerado um script.</span><span class="sxs-lookup"><span data-stu-id="0d226-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="0d226-144">Expanda o nó de categoria dos tipos de objeto dos quais você deseja gerar o script, como o nó **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="0d226-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="0d226-145">Abra o painel **Detalhes do Pesquisador de Objetos** selecionando **F7**ou abrindo o menu **Exibição** e selecionando **Detalhes do Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="0d226-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="0d226-146">Clique com o botão esquerdo do mouse em um dos objetos dos quais você deseja gerar um script.</span><span class="sxs-lookup"><span data-stu-id="0d226-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="0d226-147">Clique em Ctrl + botão esquerdo do mouse no segundo objeto do qual você deseja gerar um script.</span><span class="sxs-lookup"><span data-stu-id="0d226-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="0d226-148">Clique com o botão direito do mouse em um dos objetos selecionados e selecione **script \<object type> como**.</span><span class="sxs-lookup"><span data-stu-id="0d226-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
