---
title: 'Etapa 1: copiar o pacote da Lição 2 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bd91402-4e37-41de-ab78-8ca5a1948a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39bfc965febc401bd66b1077388021b8ccf52aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680558"
---
# <a name="step-1-copying-the-lesson-2-package"></a><span data-ttu-id="7d701-102">Etapa 1: Copiar o pacote da Lição 2</span><span class="sxs-lookup"><span data-stu-id="7d701-102">Step 1: Copying the Lesson 2 Package</span></span>
  <span data-ttu-id="7d701-103">Nesta tarefa, você criará uma cópia do pacote Lesson 2.dtsx criado na Lição 2.</span><span class="sxs-lookup"><span data-stu-id="7d701-103">In this task, you will create a copy of the Lesson 2.dtsx package that you created in Lesson 2.</span></span> <span data-ttu-id="7d701-104">Como alternativa, é possível adicionar o pacote concluído da Lição 2 incluído no tutorial do projeto e copiá-lo.</span><span class="sxs-lookup"><span data-stu-id="7d701-104">Alternatively, you can add the completed lesson 2 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="7d701-105">Você usará essa cópia nova durante toda a Lição 3.</span><span class="sxs-lookup"><span data-stu-id="7d701-105">You will use this new copy throughout the rest of Lesson 3.</span></span>  
  
### <a name="to-create-the-lesson-3-package"></a><span data-ttu-id="7d701-106">Para criar o pacote da Lição 3</span><span class="sxs-lookup"><span data-stu-id="7d701-106">To create the Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="7d701-107">Se o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools ainda não estiver aberto, clique em **Iniciar**, aponte para **Todos os Programas**, **Microsoft SQL Server 2012**e clique em **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="7d701-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="7d701-108">No menu **Arquivo** , clique em **Abrir**, clique em **Projeto/Solução**, selecione **Tutorial do SSIS** , clique em **Abrir**e clique duas vezes em **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="7d701-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="7d701-109">No Gerenciador de Soluções, clique com o botão direito do mouse em **Lesson 2.dtsx**e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="7d701-109">In Solution Explorer, right-click **Lesson 2.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="7d701-110">Em Gerenciador de Soluções, clique com o botão direito do mouse em **pacotes SSIS**e clique em **colar**.</span><span class="sxs-lookup"><span data-stu-id="7d701-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="7d701-111">Por padrão, o pacote copiado recebe o nome de Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="7d701-111">By default, the copied package is named Lesson 3.dtsx.</span></span>  
  
5.  <span data-ttu-id="7d701-112">Em Gerenciador de Soluções, clique duas vezes na **lição 3. dtsx** para abrir o pacote.</span><span class="sxs-lookup"><span data-stu-id="7d701-112">In Solution Explorer, double-click **Lesson 3.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="7d701-113">Clique com o botão direito do mouse em qualquer lugar da tela de fundo da guia **Fluxo de Controle** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7d701-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="7d701-114">Na janela Propriedades, atualize a `Name` propriedade para `Lesson 3` .</span><span class="sxs-lookup"><span data-stu-id="7d701-114">In the Properties window, update the `Name` property to `Lesson 3`.</span></span>  
  
8.  <span data-ttu-id="7d701-115">Clique na caixa da propriedade **ID** e, na lista, clique em **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="7d701-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson2-package"></a><span data-ttu-id="7d701-116">Para adicionar o pacote concluído da lição 2</span><span class="sxs-lookup"><span data-stu-id="7d701-116">To add the completed Lesson2 package</span></span>  
  
1.  <span data-ttu-id="7d701-117">Abra o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e abra o projeto do Tutorial do SSIS.</span><span class="sxs-lookup"><span data-stu-id="7d701-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="7d701-118">Em Gerenciador de Soluções, clique com o botão direito do mouse em **pacotes SSIS**e clique em **Adicionar pacote existente**.</span><span class="sxs-lookup"><span data-stu-id="7d701-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="7d701-119">Na caixa de diálogo **Adicionar Cópia do Pacote Existente** , em **Local do pacote**, selecione **Sistema de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="7d701-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="7d701-120">Clique no botão Procurar **(…)**, navegue até **Lesson 2.dtsx** no computador e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7d701-120">Click the browse **(...)** button, navigate to **Lesson 2.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="7d701-121">Para baixar todos os pacotes de lição para este tutorial, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="7d701-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="7d701-122">Navegue para os [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="7d701-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="7d701-123">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="7d701-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="7d701-124">Clique no arquivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="7d701-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="7d701-125">Copie e cole o pacote da Lição 3, conforme descrito nas etapas 3 a 8 do procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="7d701-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7d701-126">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="7d701-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7d701-127">Etapa 2: Adicionar e configurar registro em log</span><span class="sxs-lookup"><span data-stu-id="7d701-127">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
  
