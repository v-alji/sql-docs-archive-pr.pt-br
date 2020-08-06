---
title: Criar um domínio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570272"
---
# <a name="create-a-domain"></a><span data-ttu-id="88be6-102">Criar um domínio</span><span class="sxs-lookup"><span data-stu-id="88be6-102">Create a Domain</span></span>
  <span data-ttu-id="88be6-103">Este tópico descreve como criar um domínio no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="88be6-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="88be6-104">Os valores no domínio são uma representação semântica dos dados em um campo.</span><span class="sxs-lookup"><span data-stu-id="88be6-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="88be6-105">Para obter mais informações sobre domínios, consulte [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="88be6-106">Há duas maneiras de criar um novo domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="88be6-107">A primeira é durante a etapa Mapear da atividade de descoberta da base de dados de conhecimento, quando você está no processo de analisar um exemplo de dados para adicionar conhecimento a uma base de dados de conhecimento nova ou existente.</span><span class="sxs-lookup"><span data-stu-id="88be6-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="88be6-108">A segunda é durante a atividade de gerenciamento de domínio, quando, em vez de alterar um domínio existente, você cria um novo domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="88be6-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="88be6-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="88be6-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="88be6-110">Prerequisites</span></span>  
 <span data-ttu-id="88be6-111">Para criar um domínio, você precisa ter criado e aberto uma base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="88be6-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="88be6-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="88be6-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="88be6-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="88be6-113">Permissions</span></span>  
 <span data-ttu-id="88be6-114">Você deve ter a função dqs_kb_editor ou o dqs_administrator no banco de dados DQS_MAIN para criar um domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a> <span data-ttu-id="88be6-115">Criar um domínio na atividade Descoberta da Base de Dados de Conhecimento</span><span class="sxs-lookup"><span data-stu-id="88be6-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="88be6-116">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="88be6-117">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="88be6-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="88be6-118">Selecione **Descoberta da Base de Dados de Conhecimento** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.</span><span class="sxs-lookup"><span data-stu-id="88be6-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="88be6-119">Na página **Mapa** , especifique uma conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="88be6-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="88be6-120">Para obter mais informações, consulte [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="88be6-121">Na tabela **Mapeamentos** , selecione uma coluna de origem na lista suspensa da coluna **Coluna de Origem** de uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="88be6-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="88be6-122">Se não existir um domínio correspondente, clique no ícone **Criar um Domínio** .</span><span class="sxs-lookup"><span data-stu-id="88be6-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="88be6-123">Criar um domínio na atividade de gerenciamento de domínio</span><span class="sxs-lookup"><span data-stu-id="88be6-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="88be6-124">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="88be6-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="88be6-125">Selecione **Gerenciamento de Domínio** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.</span><span class="sxs-lookup"><span data-stu-id="88be6-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="88be6-126">Na página **Gerenciamento de Domínio** , clique no ícone **Criar um Domínio** acima da lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="88be6-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="88be6-127">Definir propriedades de domínio</span><span class="sxs-lookup"><span data-stu-id="88be6-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="88be6-128">Na caixa de diálogo **Criar Domínio** , insira um nome que seja exclusivo da base de dados de conhecimento e uma descrição de até 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="88be6-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88be6-129">Para obter mais informações sobre propriedades de domínio, consulte [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="88be6-130">Na lista **Tipo de Dados** , selecione um tipo de dados para os valores no domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="88be6-131">O tipo de dados pode ser **Cadeia de Caracteres** (o padrão), **Data**, **Inteiro**ou **Decimal**.</span><span class="sxs-lookup"><span data-stu-id="88be6-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="88be6-132">Selecione **Usar Valores Principais** para especificar que o valor principal em um grupo de sinônimos será gerado, e não um valor que é sinônimo dele.</span><span class="sxs-lookup"><span data-stu-id="88be6-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="88be6-133">Cancele a seleção de **Usar Valores Principais** para especificar que cada valor de sinônimo seja gerado em sua forma correta ou corrigida, e não seja substituído pelo valor principal do seu grupo.</span><span class="sxs-lookup"><span data-stu-id="88be6-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="88be6-134">Se o tipo de dados for **Cadeia de Caracteres**, selecione **Cadeia de Caracteres de Normalização** para remover caracteres especiais nos valores de domínio, o que pode melhorar a probabilidade de correspondências.</span><span class="sxs-lookup"><span data-stu-id="88be6-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="88be6-135">Na lista suspensa **Formato de Saída para** , selecione a formatação que será aplicada quando forem gerados os valores de dados no domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="88be6-136">A formatação é específica do tipo de dados selecionado na etapa 2, conforme mostrado na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="88be6-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="88be6-137">Para um valor da cadeia de caracteres, você pode especificar que a cadeia de caracteres seja gerada como maiúsculas, minúsculas ou inicial maiúscula.</span><span class="sxs-lookup"><span data-stu-id="88be6-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="88be6-138">Para um valor de data, você pode especificar o formato do dia, mês e ano.</span><span class="sxs-lookup"><span data-stu-id="88be6-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="88be6-139">Para um valor inteiro, você pode especificar o tipo de máscara de formato a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="88be6-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="88be6-140">Para um valor decimal, você pode especificar a precisão e o tipo de máscara de formato a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="88be6-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="88be6-141">Selecionar **Nenhum** na lista suspensa **Formato de Saída para** significa que nenhum dos formatos na lista será aplicado.</span><span class="sxs-lookup"><span data-stu-id="88be6-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="88be6-142">Se o tipo de dados for **Cadeia de Caracteres**, na lista suspensa **Idioma** , selecione a versão de idioma do verificador ortográfico a ser aplicada se você habilitar o verificador ortográfico.</span><span class="sxs-lookup"><span data-stu-id="88be6-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="88be6-143">Se o tipo de dados for **Cadeia de Caracteres**, selecione **Habilitar Verificador Ortográfico** para executar todos os valores da cadeia de caracteres ao popular o domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="88be6-144">Se o tipo de dados for **Cadeia de Caracteres**, selecione **Desabilitar Algoritmos de Erro de Sintaxe** para popular o domínio sem verificar se existem erros de sintaxe em valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="88be6-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="88be6-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88be6-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="88be6-146">Clique em **Concluir** para concluir a atividade de gerenciamento de domínio, conforme descrito em [Terminar a atividade Gerenciamento de Domínio](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="88be6-147">Acompanhamento: após a criação de um domínio</span><span class="sxs-lookup"><span data-stu-id="88be6-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="88be6-148">Depois que você criar um domínio, poderá executar outras tarefas de gerenciamento de domínio, executar a descoberta da base de dados de conhecimento para adicionar conhecimento ao domínio ou adicionar uma política de correspondência ao domínio.</span><span class="sxs-lookup"><span data-stu-id="88be6-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="88be6-149">Para obter mais informações, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md) ou [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="88be6-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
