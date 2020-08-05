---
title: Assistente de importação de projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574197"
---
# <a name="import-project-wizard"></a><span data-ttu-id="533bf-102">Assistente para Importação de Projeto</span><span class="sxs-lookup"><span data-stu-id="533bf-102">Import Project Wizard</span></span>
  <span data-ttu-id="533bf-103">Use o Assistente de Projeto de Importação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para criar um novo projeto do Integration Services baseado em um existente.</span><span class="sxs-lookup"><span data-stu-id="533bf-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="533bf-104">Importe os projetos que já foram implantados para o catálogo do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou importe projetos de um arquivo de implantação de projeto (extensão .ispac).</span><span class="sxs-lookup"><span data-stu-id="533bf-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="533bf-105">Para criar um projeto com base em um projeto em arquivo .ispac ou em catálogo</span><span class="sxs-lookup"><span data-stu-id="533bf-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="533bf-106">Clique em **arquivo**, aponte para **novo**e clique em projeto.</span><span class="sxs-lookup"><span data-stu-id="533bf-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="533bf-107">Expanda **Business Intelligence**e clique em **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="533bf-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="533bf-108">Selecione **Assistente de Importação do Integration Services** no painel central, digite um **nome** para a solução, projeto, especifique a **pasta** para o projeto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="533bf-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="533bf-109">Você deverá ver o **Assistente de Importação de Projeto do Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="533bf-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="533bf-110">Esse assistente cria um novo projeto do Integration Services com base em um projeto existente.</span><span class="sxs-lookup"><span data-stu-id="533bf-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="533bf-111">Clique em **Avançar** na página **Introdução** para ver a página **Selecionar Origem** .</span><span class="sxs-lookup"><span data-stu-id="533bf-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="533bf-112">Especifique se você deseja importar o projeto de um arquivo .ispac ou de um catálogo.</span><span class="sxs-lookup"><span data-stu-id="533bf-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="533bf-113">Se você selecionar a opção **Arquivo de implantação de projeto** , especifique o caminho do arquivo .ispac.</span><span class="sxs-lookup"><span data-stu-id="533bf-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="533bf-114">Se você selecionar a opção **Catálogo do Integration Services** , especifique o nome de instância do servidor de banco de dados na qual o catálogo existe e o caminho para o projeto no catálogo.</span><span class="sxs-lookup"><span data-stu-id="533bf-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="533bf-115">Clique em **Avançar** na página **Selecionar Origem** para ver a página **Revisão** .</span><span class="sxs-lookup"><span data-stu-id="533bf-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="533bf-116">Revise as informações exibidas na página sobre a operação de importação que o assistente irá executar.</span><span class="sxs-lookup"><span data-stu-id="533bf-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="533bf-117">Clique em **Importar** para criar um novo projeto do Integration Services baseado naquele que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="533bf-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="533bf-118">A página **Resultados** deverá exibir os resultados da operação de importação que o assistente executou.</span><span class="sxs-lookup"><span data-stu-id="533bf-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="533bf-119">Clique em **Salvar Relatório** para salvar o relatório em um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="533bf-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="533bf-120">Clique em **Fechar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="533bf-120">Click **Close** to close the wizard.</span></span>  
  
  
