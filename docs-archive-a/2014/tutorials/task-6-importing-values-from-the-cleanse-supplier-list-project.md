---
title: 'Tarefa 6: importando valores do projeto de lista de fornecedores de limpeza | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570387"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="176a0-102">Tarefa 6: Importando valores do projeto Limpar Lista de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="176a0-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="176a0-103">Nesta tarefa, você importará o conhecimento de qualidade de dados adquirido durante o processo de limpeza.</span><span class="sxs-lookup"><span data-stu-id="176a0-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="176a0-104">Consulte [importando valores de projeto de limpeza em um](https://msdn.microsoft.com/library/hh479581.aspx) tópico de domínio para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="176a0-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="176a0-105">Você também exporta a base de dados de conhecimento para um arquivo do DQS antes de publicar a base de dados de conhecimento dos **fornecedores** atualizados.</span><span class="sxs-lookup"><span data-stu-id="176a0-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="176a0-106">Na página principal do **cliente do DQS**, clique na **seta para a direita** ao lado de **fornecedores** em bases de **dados de conhecimento recentes** e clique em **Gerenciamento de domínio**.</span><span class="sxs-lookup"><span data-stu-id="176a0-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="176a0-107">Clique em **email de contato** na lista de domínios e alterne para a guia valores de **domínio** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="176a0-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="176a0-108">Clique na **seta para baixo** ao lado do ícone **importar valores** na barra de ferramentas e clique em **importar valores do projeto**.</span><span class="sxs-lookup"><span data-stu-id="176a0-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="176a0-109">![Botão de barra de ferramentas Importar Valores de Projeto](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Botão de barra de ferramentas Importar Valores de Projeto")</span><span class="sxs-lookup"><span data-stu-id="176a0-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="176a0-110">Na caixa de diálogo **importar valores do projeto** , selecione o projeto de **lista limpar fornecedor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="176a0-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="176a0-111">Observe que todos os emails são importados juntamente com as duas correções feitas durante a limpeza interativa.</span><span class="sxs-lookup"><span data-stu-id="176a0-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="176a0-112">Role a tela para ver as duas correções.</span><span class="sxs-lookup"><span data-stu-id="176a0-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="176a0-113">Valor</span><span class="sxs-lookup"><span data-stu-id="176a0-113">Value</span></span>|<span data-ttu-id="176a0-114">Corrigir para</span><span class="sxs-lookup"><span data-stu-id="176a0-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="176a0-115">Repita a etapa anterior da importação de valores de projeto para o domínio de **país** e observe que uma nova entrada é adicionada para corrigir o **estado United** para **Estados Unidos** (com ').</span><span class="sxs-lookup"><span data-stu-id="176a0-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="176a0-116">Valor</span><span class="sxs-lookup"><span data-stu-id="176a0-116">Value</span></span>|<span data-ttu-id="176a0-117">Corrigir para</span><span class="sxs-lookup"><span data-stu-id="176a0-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="176a0-118">United State</span><span class="sxs-lookup"><span data-stu-id="176a0-118">United State</span></span>|<span data-ttu-id="176a0-119">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="176a0-119">United States</span></span>|  
  
7.  <span data-ttu-id="176a0-120">Para ver os valores de domínio antigos, desmarque **Mostrar somente nova** caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="176a0-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="176a0-121">Repita a etapa anterior da importação de valores de projeto para o domínio de **nome do fornecedor** .</span><span class="sxs-lookup"><span data-stu-id="176a0-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="176a0-122">Por padrão, após a importação, você verá apenas os novos valores.</span><span class="sxs-lookup"><span data-stu-id="176a0-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="176a0-123">Para ver todos os valores, desmarque **Mostrar somente nova** caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="176a0-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="176a0-124">Você enriqueceu a base de dados de conhecimento dos **fornecedores** com o que aprendeu na atividade de limpeza.</span><span class="sxs-lookup"><span data-stu-id="176a0-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="176a0-125">Quanto mais forte for a base de dados de conhecimento, melhores serão os resultados da limpeza.</span><span class="sxs-lookup"><span data-stu-id="176a0-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="176a0-126">Não há valores de importação possíveis para um domínio composto.</span><span class="sxs-lookup"><span data-stu-id="176a0-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="176a0-127">Clique no ícone **Exportar base de dados de conhecimento** na barra de ferramentas e clique em **Exportar base de dados de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="176a0-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="176a0-128">![Menu Exportar Base de Dados de Conhecimento](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Menu Exportar Base de Dados de Conhecimento")</span><span class="sxs-lookup"><span data-stu-id="176a0-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="176a0-129">Navegue até a pasta tutorial, digite **suppliers. DQS** para o **nome do arquivo**e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="176a0-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="176a0-130">Você pode usar esse arquivo do DQS para criar uma nova base de dados de conhecimento baseada nele.</span><span class="sxs-lookup"><span data-stu-id="176a0-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="176a0-131">Clique em **OK** para fechar a caixa de mensagem **Exportar base de dados de conhecimento-fornecedores** .</span><span class="sxs-lookup"><span data-stu-id="176a0-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="176a0-132">Clique em **concluir** para concluir a atividade.</span><span class="sxs-lookup"><span data-stu-id="176a0-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="176a0-133">Clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="176a0-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="176a0-134">Clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="176a0-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="176a0-135">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="176a0-135">Next Step</span></span>  
 [<span data-ttu-id="176a0-136">Lição 3: Correspondendo dados para remover duplicatas da lista de fornecedores</span><span class="sxs-lookup"><span data-stu-id="176a0-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
