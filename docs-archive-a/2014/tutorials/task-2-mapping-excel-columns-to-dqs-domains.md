---
title: 'Tarefa 2: mapeando colunas do Excel para domínios do DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582234"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="87597-102">Tarefa 2: Mapeando colunas do Excel para domínios do DQS</span><span class="sxs-lookup"><span data-stu-id="87597-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="87597-103">Na página **Mapear** , selecione **Arquivo do Excel** em **Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="87597-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="87597-104">Clique em **procurar**, selecione **Suppliers.xlsx**e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="87597-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="87597-105">Selecione **IncomingSuppliers $** para a **planilha**.</span><span class="sxs-lookup"><span data-stu-id="87597-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="87597-106">Mapeie as colunas conforme mostrado na tabela e na captura de tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="87597-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="87597-107">Ao criar mapeamentos para o domínio de **estado** , clique no botão **Adicionar um mapeamento de coluna** na barra de ferramentas localizada logo acima da lista.</span><span class="sxs-lookup"><span data-stu-id="87597-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="87597-108">Você não está usando a coluna/domínio da **ID do fornecedor** para limpeza.</span><span class="sxs-lookup"><span data-stu-id="87597-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="87597-109">Você usará o domínio da **ID do fornecedor** mais tarde na atividade de correspondência.</span><span class="sxs-lookup"><span data-stu-id="87597-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="87597-110">Coluna do Excel</span><span class="sxs-lookup"><span data-stu-id="87597-110">Excel column</span></span>|<span data-ttu-id="87597-111">Domínio do DQS</span><span class="sxs-lookup"><span data-stu-id="87597-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="87597-112">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="87597-112">Supplier Name</span></span>|<span data-ttu-id="87597-113">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="87597-113">Supplier Name</span></span>|  
    |<span data-ttu-id="87597-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="87597-114">ContactEmailAddress</span></span>|<span data-ttu-id="87597-115">Email de contato</span><span class="sxs-lookup"><span data-stu-id="87597-115">Contact Email</span></span>|  
    |<span data-ttu-id="87597-116">Linha de Endereço</span><span class="sxs-lookup"><span data-stu-id="87597-116">Address Line</span></span>|<span data-ttu-id="87597-117">Linha de Endereço</span><span class="sxs-lookup"><span data-stu-id="87597-117">Address Line</span></span>|  
    |<span data-ttu-id="87597-118">City</span><span class="sxs-lookup"><span data-stu-id="87597-118">City</span></span>|<span data-ttu-id="87597-119">City</span><span class="sxs-lookup"><span data-stu-id="87597-119">City</span></span>|  
    |<span data-ttu-id="87597-120">Estado</span><span class="sxs-lookup"><span data-stu-id="87597-120">State</span></span>|<span data-ttu-id="87597-121">Estado</span><span class="sxs-lookup"><span data-stu-id="87597-121">State</span></span>|  
    |<span data-ttu-id="87597-122">País (clique na barra de ferramentas **(adicionar um mapeamento de coluna)** para adicionar uma linha)</span><span class="sxs-lookup"><span data-stu-id="87597-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="87597-123">País</span><span class="sxs-lookup"><span data-stu-id="87597-123">Country</span></span>|  
    |<span data-ttu-id="87597-124">Zip Code</span><span class="sxs-lookup"><span data-stu-id="87597-124">Zip Code</span></span>|<span data-ttu-id="87597-125">Zip</span><span class="sxs-lookup"><span data-stu-id="87597-125">Zip</span></span>|  
  
     <span data-ttu-id="87597-126">![Mapeamentos de colunas do Excel para Domínios](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mapeamentos de colunas do Excel para Domínios")</span><span class="sxs-lookup"><span data-stu-id="87597-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="87597-127">Como você mapeou todos os domínios individuais dentro do domínio composto de **validação de endereço** , o domínio composto participa automaticamente do processo de limpeza.</span><span class="sxs-lookup"><span data-stu-id="87597-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="87597-128">Clique no botão **Exibir/selecionar domínios compostos** para ver se o domínio composto de **validação de endereço** está selecionado automaticamente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="87597-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="87597-129">![Caixa de diálogo Exibir/Selecionar Domínios Compostos](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Caixa de diálogo Exibir/Selecionar Domínios Compostos")</span><span class="sxs-lookup"><span data-stu-id="87597-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="87597-130">Clique em **Avançar** para alternar para a página **limpar** .</span><span class="sxs-lookup"><span data-stu-id="87597-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="87597-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="87597-131">Next Step</span></span>  
 [<span data-ttu-id="87597-132">Tarefa 3: Limpando dados em relação à base de dados de conhecimento de fornecedores</span><span class="sxs-lookup"><span data-stu-id="87597-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
