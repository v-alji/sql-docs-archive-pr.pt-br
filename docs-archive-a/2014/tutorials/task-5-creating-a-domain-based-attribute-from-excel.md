---
title: 'Tarefa 5: Criando um atributo baseado em domínio do Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680717"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="0f3ec-102">Tarefa 5: Criando um atributo baseado em domínio no Excel</span><span class="sxs-lookup"><span data-stu-id="0f3ec-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="0f3ec-103">Nesta tarefa, você converte o atributo de **estado** da entidade **Supplier** como um **atributo baseado em domínio**.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="0f3ec-104">Depois de configurar o atributo de estado para ser um baseado em domínio e publicá-lo no MDS, uma nova entidade chamada **State** será criada no servidor MDS com todos os valores na coluna e o atributo **State** da entidade **Supplier** será populado com valores da entidade **State** .</span><span class="sxs-lookup"><span data-stu-id="0f3ec-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="0f3ec-105">Agora, o modelo **suppliers** deve ter duas entidades: **Supplier** e **State** , em que o atributo **State** da entidade **Supplier** é um atributo baseado em domínio que depende da entidade **State** .</span><span class="sxs-lookup"><span data-stu-id="0f3ec-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="0f3ec-106">Alternar para a janela do **Excel** que foi **limpa e correspondente Suppliers.xlsx** aberto.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="0f3ec-107">Clique no botão **Atualizar** na faixa de faixas para obter as atualizações mais recentes do MDS.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="0f3ec-108">Você deverá ver os mais dois registros se tiver executado a **tarefa 4**opcional.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="0f3ec-109">Clique em **estado** do nome da coluna (célula **i1**) na **linha de cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="0f3ec-110">![Excel - Botão Propriedades de Atributo](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Botão Propriedades de Atributo")</span><span class="sxs-lookup"><span data-stu-id="0f3ec-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="0f3ec-111">Clique em **Propriedades do atributo** na faixa de faixas.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="0f3ec-112">Na caixa de diálogo **Propriedades do atributo** , selecione **lista restrita (baseada em domínio)** para o **tipo de atributo**.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="0f3ec-113">Digite **estado** para o **novo nome de entidade** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="0f3ec-114">![Excel - Caixa de diálogo Propriedades de Atributo](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Caixa de diálogo Propriedades de Atributo")</span><span class="sxs-lookup"><span data-stu-id="0f3ec-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="0f3ec-115">Agora, no Excel, você deve ver a **seta para baixo** ao clicar em qualquer valor na coluna **estado** .</span><span class="sxs-lookup"><span data-stu-id="0f3ec-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="0f3ec-116">Você poderá alterar o valor usando a lista suspensa se necessário.</span><span class="sxs-lookup"><span data-stu-id="0f3ec-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="0f3ec-117">![Excel - Lista suspensa com estados](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Lista suspensa com estados")</span><span class="sxs-lookup"><span data-stu-id="0f3ec-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0f3ec-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="0f3ec-118">Next Step</span></span>  
 [<span data-ttu-id="0f3ec-119">Tarefa 6: Verificar se o atributo baseado em domínio foi criado usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="0f3ec-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
