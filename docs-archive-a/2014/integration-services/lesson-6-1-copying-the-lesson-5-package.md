---
title: 'Etapa 1: copiar o pacote da Lição 5 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583729"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="5a3d4-102">Etapa 1: Copiar o pacote da Lição 5</span><span class="sxs-lookup"><span data-stu-id="5a3d4-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="5a3d4-103">Nesta tarefa, você criará uma cópia do pacote Lesson 5.dtsx criado na lição 5.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="5a3d4-104">Como alternativa, é possível adicionar o pacote concluído da Lição 5 incluído com o tutorial do projeto e copiá-lo.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="5a3d4-105">Você usará esta cópia nova ao longo de toda a lição 6.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="5a3d4-106">Para copiar o pacote da Lição 5</span><span class="sxs-lookup"><span data-stu-id="5a3d4-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="5a3d4-107">Se o SQL Server Data Tools ainda não estiver aberto, clique em Iniciar, aponte para Todos os Programas, aponte para Microsoft SQL Server 2012 e clique em SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="5a3d4-108">No menu Arquivo, clique em Abrir, clique em Projeto/Solução, selecione Tutorial do SSIS, clique em Abrir e clique duas vezes em SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="5a3d4-109">No Gerenciador de Soluções, clique com o botão direito do mouse em Lesson 5.dtsx e, em seguida, clique em Copiar.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="5a3d4-110">No Gerenciador de Soluções, clique com o botão direito do mouse em Pacotes SSIS e clique em Colar.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="5a3d4-111">Por padrão, o pacote copiado recebe o nome de Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="5a3d4-112">No Gerenciador de Soluções, clique duas vezes em Lesson 6.dtsx para abrir o pacote.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="5a3d4-113">Clique com o botão direito do mouse em qualquer local do plano de fundo da guia Fluxo de Controle e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="5a3d4-114">Na janela Propriedades, atualize a propriedade de Nome da lição 6.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="5a3d4-115">Clique na caixa da propriedade ID, clique na seta suspensa e em \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="5a3d4-116">Para adicionar o pacote concluído da lição 5</span><span class="sxs-lookup"><span data-stu-id="5a3d4-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="5a3d4-117">Abra o SQL Server Data Tools e abra o projeto do Tutorial do SSIS.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="5a3d4-118">No Gerenciador de Soluções, clique com o botão direito do mouse em Pacotes SSIS e clique em Adicionar Pacote Existente.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="5a3d4-119">Na caixa de diálogo Adicionar Cópia do Pacote Existente, em Local do Pacote, selecione Sistema de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="5a3d4-120">Clique no botão Procurar (...), Lesson 5.dtsx no computador e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="5a3d4-121">Para baixar todos os pacotes de lição para este tutorial, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="5a3d4-122">Navegue para os [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="5a3d4-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="5a3d4-123">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="5a3d4-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="5a3d4-124">Clique no arquivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="5a3d4-125">Copie e cole o pacote da Lição 5 conforme descrito nas etapas de 3 a 8 do procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="5a3d4-126">Depois de copiar o pacote da lição 5, se você tiver atualmente os pacotes das lições anteriores em sua solução, clique com o botão direito do mouse em cada pacote das lições de 1 a 5 e clique em Excluir do Projeto.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="5a3d4-127">Ao terminar, você deve ter apenas a Lição 6.dtsx em sua solução.</span><span class="sxs-lookup"><span data-stu-id="5a3d4-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5a3d4-128">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="5a3d4-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5a3d4-129">Etapa 2: Convertendo o projeto para o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="5a3d4-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
