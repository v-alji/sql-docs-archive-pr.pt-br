---
title: 'Tarefa 7: adicionando a transformação de limpeza DQS ao fluxo de dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570381"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="6477c-102">Tarefa 7: Adicionando a Transformação de Limpeza DQS ao fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="6477c-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="6477c-103">Nesta tarefa, você adiciona a Transformação de Limpeza DQS ao fluxo de dados para limpar os dados do fornecedor de entrada usando o DQS.</span><span class="sxs-lookup"><span data-stu-id="6477c-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="6477c-104">Consulte **[transformação de limpeza DQS](https://msdn.microsoft.com/library/ee677619.aspx)** para obter mais detalhes sobre a transformação.</span><span class="sxs-lookup"><span data-stu-id="6477c-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="6477c-105">Clique com o botão direito do mouse em **limpeza DQS** na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="6477c-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="6477c-106">Digite **limpar dados do fornecedor**e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="6477c-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="6477c-107">Selecione **ler dados do fornecedor do arquivo do Excel**; Arraste o conector azul para **limpar os dados do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="6477c-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="6477c-108">Os componentes estão conectados agora.</span><span class="sxs-lookup"><span data-stu-id="6477c-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="6477c-109">![Ler dados do fornecedor-> limpar dados do fornecedor](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Ler Dados de Fornecedor -> Limpar Dados de Fornecedor")</span><span class="sxs-lookup"><span data-stu-id="6477c-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="6477c-110">Clique duas vezes em **limpar dados do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="6477c-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="6477c-111">No **Editor de transformação de limpeza DQS**, clique em **novo** ao lado da **lista suspensa Gerenciador de conexões de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="6477c-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="6477c-112">Na caixa de diálogo **Gerenciador de conexões de limpeza DQS** , digite **(local)** ou **ponto** (.) para se conectar ao servidor local.</span><span class="sxs-lookup"><span data-stu-id="6477c-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="6477c-113">Esta lição supõe que você tenha o DQS instalado em um servidor local.</span><span class="sxs-lookup"><span data-stu-id="6477c-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="6477c-114">Clique em **testar conexão** para testar a conexão com o servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="6477c-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="6477c-115">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6477c-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="6477c-116">Selecione os **fornecedores** para a **base de dados de conhecimento de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="6477c-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="6477c-117">![Caixa de diálogo Editor de Transformação de Limpeza DQS - KB de Fornecedores](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Caixa de diálogo Editor de Transformação de Limpeza DQS - KB de Fornecedores")</span><span class="sxs-lookup"><span data-stu-id="6477c-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="6477c-118">Alterne para a guia **mapeamento** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="6477c-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="6477c-119">Nas **colunas de entrada disponíveis**, selecione **nome do fornecedor**, **ContactEmailAddress**, **linha de endereço**, **cidade**, **estado**, **país**e **CEP** marcando as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="6477c-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="6477c-120">![Editor de Transformação de Limpeza DQS - Mapeamentos](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Editor de Transformação de Limpeza DQS - Mapeamentos")</span><span class="sxs-lookup"><span data-stu-id="6477c-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="6477c-121">No painel inferior, mapeie essas colunas usando listas suspensas na coluna **domínio** :</span><span class="sxs-lookup"><span data-stu-id="6477c-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="6477c-122">Column</span><span class="sxs-lookup"><span data-stu-id="6477c-122">Column</span></span>|<span data-ttu-id="6477c-123">Domínio</span><span class="sxs-lookup"><span data-stu-id="6477c-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="6477c-124">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="6477c-124">Supplier Name</span></span>|<span data-ttu-id="6477c-125">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="6477c-125">Supplier Name</span></span>|  
    |<span data-ttu-id="6477c-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="6477c-126">ContactEmailAddress</span></span>|<span data-ttu-id="6477c-127">Email de contato</span><span class="sxs-lookup"><span data-stu-id="6477c-127">Contact Email</span></span>|  
    |<span data-ttu-id="6477c-128">Linha de Endereço</span><span class="sxs-lookup"><span data-stu-id="6477c-128">Address Line</span></span>|<span data-ttu-id="6477c-129">Linha de Endereço</span><span class="sxs-lookup"><span data-stu-id="6477c-129">Address Line</span></span>|  
    |<span data-ttu-id="6477c-130">City</span><span class="sxs-lookup"><span data-stu-id="6477c-130">City</span></span>|<span data-ttu-id="6477c-131">City</span><span class="sxs-lookup"><span data-stu-id="6477c-131">City</span></span>|  
    |<span data-ttu-id="6477c-132">Estado</span><span class="sxs-lookup"><span data-stu-id="6477c-132">State</span></span>|<span data-ttu-id="6477c-133">Estado</span><span class="sxs-lookup"><span data-stu-id="6477c-133">State</span></span>|  
    |<span data-ttu-id="6477c-134">País</span><span class="sxs-lookup"><span data-stu-id="6477c-134">Country</span></span>|<span data-ttu-id="6477c-135">País</span><span class="sxs-lookup"><span data-stu-id="6477c-135">Country</span></span>|  
    |<span data-ttu-id="6477c-136">Zip Code</span><span class="sxs-lookup"><span data-stu-id="6477c-136">Zip Code</span></span>|<span data-ttu-id="6477c-137">Zip</span><span class="sxs-lookup"><span data-stu-id="6477c-137">Zip</span></span>|  
  
12. <span data-ttu-id="6477c-138">Clique em **OK** para fechar a caixa de diálogo **Editor de transformação de limpeza DQS** .</span><span class="sxs-lookup"><span data-stu-id="6477c-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6477c-139">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6477c-139">Next Step</span></span>  
 [<span data-ttu-id="6477c-140">Tarefa 8: Adicionando a Transformação Divisão Condicional para dividir a saída da limpeza</span><span class="sxs-lookup"><span data-stu-id="6477c-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
