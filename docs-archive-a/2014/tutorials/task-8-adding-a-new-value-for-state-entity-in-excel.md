---
title: 'Tarefa 8: adicionando um novo valor para a entidade de estado no Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681938"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="6880d-102">Tarefa 8: Adicionando um novo valor à entidade State do Excel</span><span class="sxs-lookup"><span data-stu-id="6880d-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="6880d-103">Nesta tarefa, você adicionará um valor para a entidade State no Excel e publicará a alteração no servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="6880d-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="6880d-104">Adicione uma **folha de trabalho** no Excel clicando na guia novo na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="6880d-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="6880d-105">![Excel - Nova guia Pasta de Trabalho](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - Nova guia Pasta de Trabalho")</span><span class="sxs-lookup"><span data-stu-id="6880d-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="6880d-106">No **Excel**, clique na guia **dados mestres** no menu e, em seguida, clique em **Mostrar Explorer** na faixa de faixas.</span><span class="sxs-lookup"><span data-stu-id="6880d-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="6880d-107">No **Data Explorer mestre**, selecione **fornecedores** para **modelo**.</span><span class="sxs-lookup"><span data-stu-id="6880d-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="6880d-108">Você deve ver duas entidades: **fornecedor** e **estado** na lista de entidades.</span><span class="sxs-lookup"><span data-stu-id="6880d-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="6880d-109">Clique duas vezes em **estado** na lista.</span><span class="sxs-lookup"><span data-stu-id="6880d-109">Double-click **State** in the list.</span></span> <span data-ttu-id="6880d-110">Todos os membros da entidade de **estado** do MDS devem ser exibidos na planilha.</span><span class="sxs-lookup"><span data-stu-id="6880d-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="6880d-111">Agora, adicione uma linha no final com os seguintes valores: **Carolina do Norte** para **nome** e **NC** para **código**.</span><span class="sxs-lookup"><span data-stu-id="6880d-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="6880d-112">A codificação por cores diferencia qualquer registro novo/atualizado dos outros registros.</span><span class="sxs-lookup"><span data-stu-id="6880d-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="6880d-113">![Excel - Adicionar Carolina do Norte a Estados](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Adicionar Carolina do Norte a Estados")</span><span class="sxs-lookup"><span data-stu-id="6880d-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="6880d-114">Clique em **publicar** na faixa de faixas para publicar a alteração no MDS.</span><span class="sxs-lookup"><span data-stu-id="6880d-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="6880d-115">![Excel - Botão Publicar na guia Dados Mestre](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Botão Publicar na guia Dados Mestre")</span><span class="sxs-lookup"><span data-stu-id="6880d-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="6880d-116">Na caixa de diálogo **publicar e anotar** , observe que o **uso da mesma anotação para todas as alterações** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="6880d-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="6880d-117">Você pode inserir uma anotação única de todas as alterações aqui.</span><span class="sxs-lookup"><span data-stu-id="6880d-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="6880d-118">Selecione a opção **revisar alterações e fornecer anotações individualmente** para fornecer anotação para cada alteração (neste caso, apenas uma).</span><span class="sxs-lookup"><span data-stu-id="6880d-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="6880d-119">![Excel - Caixa de diálogo Publicar e Anotar](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Caixa de diálogo Publicar e Anotar")</span><span class="sxs-lookup"><span data-stu-id="6880d-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="6880d-120">Clique em **publicar** para publicar dados no MDS.</span><span class="sxs-lookup"><span data-stu-id="6880d-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="6880d-121">Observe que a **codificação por cores** para a linha com a Carolina do **norte** como o **estado** é igual a outros registros agora.</span><span class="sxs-lookup"><span data-stu-id="6880d-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="6880d-122">**Opcional:** Verifique se o novo membro (NC) foi adicionado à entidade de **estado** usando o **Gerenciador** no **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="6880d-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="6880d-123">No Excel, clique com o botão direito do mouse na planilha de **estado** na parte inferior e clique em **excluir** para excluir a planilha.</span><span class="sxs-lookup"><span data-stu-id="6880d-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="6880d-124">Excluir a planilha não exclui os dados do servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="6880d-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6880d-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6880d-125">Next Step</span></span>  
 [<span data-ttu-id="6880d-126">Tarefa 9: Criando uma hierarquia derivada usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="6880d-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
