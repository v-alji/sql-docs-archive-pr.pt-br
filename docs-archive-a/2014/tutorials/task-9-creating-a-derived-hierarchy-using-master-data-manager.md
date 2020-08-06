---
title: 'Tarefa 9: criando uma hierarquia derivada usando Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685985"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="27cc8-102">Tarefa 9: Criando uma hierarquia derivada usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="27cc8-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="27cc8-103">Nesta tarefa, você criará uma hierarquia derivada usando o Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="27cc8-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="27cc8-104">Essa hierarquia derivada é derivada das relações de atributo baseadas em domínio entre as entidades **fornecedor** e **estado** .</span><span class="sxs-lookup"><span data-stu-id="27cc8-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="27cc8-105">Alterne para a página principal do **Master Data Manager** clicando em **SQL Server 2012 Master Data Services** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="27cc8-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="27cc8-106">Clique em **Administração do Sistema** na seção **Tarefas Administrativas** .</span><span class="sxs-lookup"><span data-stu-id="27cc8-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="27cc8-107">Passe o mouse sobre **gerenciar** na barra de menus e clique em **hierarquias derivadas**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="27cc8-108">![Menu Gerenciar - Hierarquias Derivadas selecionada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Menu Gerenciar - Hierarquias Derivadas selecionada")</span><span class="sxs-lookup"><span data-stu-id="27cc8-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="27cc8-109">Clique no botão **Adicionar hierarquia derivada (+)** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="27cc8-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="27cc8-110">![Botão Adicionar Hierarquia Derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Botão Adicionar Hierarquia Derivada")</span><span class="sxs-lookup"><span data-stu-id="27cc8-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="27cc8-111">Digite **SuppliersInState** para o **nome da hierarquia derivada**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="27cc8-112">Clique no botão **salvar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="27cc8-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="27cc8-113">![Botão Salvar Hierarquia Derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Botão Salvar Hierarquia Derivada")</span><span class="sxs-lookup"><span data-stu-id="27cc8-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="27cc8-114">Arraste **fornecedor** dos **níveis disponíveis: SuppliersInState** para **os níveis atuais: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="27cc8-115">![Entidades e Hierarquias Disponíveis para nível atual](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Entidades e Hierarquias Disponíveis para nível atual")</span><span class="sxs-lookup"><span data-stu-id="27cc8-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="27cc8-116">Arraste o **estado** dos **níveis disponíveis: SuppliersInState** para **os níveis atuais: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="27cc8-117">A tela deve ter **níveis atuais** , conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="27cc8-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="27cc8-118">![Visualização e níveis atuais de Hierarquia Derivada](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Visualização e níveis atuais de Hierarquia Derivada")</span><span class="sxs-lookup"><span data-stu-id="27cc8-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="27cc8-119">Na janela de **Visualização** , expanda **NY {Nova York}** e você verá um fornecedor nesse estado, conforme mostrado na imagem anterior.</span><span class="sxs-lookup"><span data-stu-id="27cc8-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="27cc8-120">Alterne para a página principal do **Master Data Manager** clicando em **SQL Server 2012 Master Data Services** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="27cc8-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="27cc8-121">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="27cc8-122">Passe o mouse sobre **hierarquias** e clique em **derivado: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="27cc8-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="27cc8-123">![Hierarquias Derivadas: Menu SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarquias Derivadas: Menu SuppliersInState")</span><span class="sxs-lookup"><span data-stu-id="27cc8-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="27cc8-124">Clique em qualquer nó de **estado** no **modo de exibição de árvore** e você deverá ver os fornecedores nesse estado no painel direito.</span><span class="sxs-lookup"><span data-stu-id="27cc8-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="27cc8-125">![Hierarquia Derivada no Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Hierarquia Derivada no Explorer")</span><span class="sxs-lookup"><span data-stu-id="27cc8-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="27cc8-126">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="27cc8-126">Next Step</span></span>  
 [<span data-ttu-id="27cc8-127">Lição 5: Automatizando a limpeza e a correspondência usando o SSIS</span><span class="sxs-lookup"><span data-stu-id="27cc8-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
