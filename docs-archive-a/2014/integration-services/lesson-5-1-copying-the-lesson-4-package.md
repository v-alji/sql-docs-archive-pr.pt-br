---
title: 'Etapa 1: copiar o pacote da Lição 4 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583161"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="0cfcb-102">Etapa 1: Copiar o pacote da Lição 4</span><span class="sxs-lookup"><span data-stu-id="0cfcb-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="0cfcb-103">Nesta tarefa, você criará uma cópia do pacote Lesson 4.dtsx criado na Lição 4.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="0cfcb-104">Como alternativa, é possível adicionar o pacote concluído da Lição 4 incluído no tutorial do projeto e copiá-lo.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="0cfcb-105">Você usará essa cópia nova durante toda a Lição 5.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="0cfcb-106">Para copiar o pacote da Lição 4</span><span class="sxs-lookup"><span data-stu-id="0cfcb-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="0cfcb-107">Se o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools ainda não estiver aberto, clique em **Iniciar**, aponte para **Todos os Programas**, **Microsoft SQL Server 2012**e clique em **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="0cfcb-108">No menu **Arquivo** , clique em **Abrir**, clique em **Projeto/Solução**, selecione **Tutorial do SSIS** , clique em **Abrir**e clique duas vezes em **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="0cfcb-109">No Gerenciador de Soluções, clique com o botão direito do mouse em **Lesson 4.dtsx**e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="0cfcb-110">Em Gerenciador de Soluções, clique com o botão direito do mouse em **pacotes SSIS**e clique em **colar**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="0cfcb-111">Por padrão, o pacote copiado recebe o nome de Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="0cfcb-112">No Gerenciador de Soluções, clique duas vezes em **Lesson 5.dtsx** para abrir o pacote.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="0cfcb-113">Clique com o botão direito do mouse em qualquer lugar no plano de fundo da guia **fluxo de controle** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="0cfcb-114">Na janela Propriedades, atualize a `Name` propriedade para `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="0cfcb-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="0cfcb-115">Clique na caixa da propriedade **ID** , clique na seta suspensa e, em seguida, clique em **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="0cfcb-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="0cfcb-116">Para adicionar o pacote concluído da Lição 4</span><span class="sxs-lookup"><span data-stu-id="0cfcb-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="0cfcb-117">Abra as Ferramentas de Dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e abra o projeto do Tutorial do SSIS.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="0cfcb-118">Em Gerenciador de Soluções, clique com o botão direito do mouse em **pacotes SSIS**e clique em **Adicionar pacote existente**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="0cfcb-119">Na caixa de diálogo **Adicionar Cópia do Pacote Existente** , em **Local do pacote**, selecione **Sistema de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="0cfcb-120">Clique no botão procurar **(...)** , navegue até a **lição 4. dtsx** em seu computador e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="0cfcb-121">Para baixar todos os pacotes de lição para este tutorial, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="0cfcb-122">Navegue para os [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="0cfcb-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="0cfcb-123">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="0cfcb-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="0cfcb-124">Clique no arquivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="0cfcb-125">Copie e cole o pacote da Lição 4, conforme descrito nas etapas 3 a 8 do procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="0cfcb-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0cfcb-126">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="0cfcb-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0cfcb-127">Etapa 2: Habilitar e configurar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="0cfcb-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
