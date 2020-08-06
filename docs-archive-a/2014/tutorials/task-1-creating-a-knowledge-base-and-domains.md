---
title: 'Tarefa 1: criando uma base de dados de conhecimento e domínios | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680239"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="8090c-102">Tarefa 1: Criando a base de dados de conhecimento e domínios</span><span class="sxs-lookup"><span data-stu-id="8090c-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="8090c-103">Nesta tarefa, você criará a base de dados de conhecimento **suppliers** e criará domínios que são usados para limpeza e dados correspondentes para remover duplicatas.</span><span class="sxs-lookup"><span data-stu-id="8090c-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="8090c-104">Iniciar **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="8090c-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="8090c-105">Clique **em Iniciar**, aponte **para todos os programas**, clique em **Microsoft SQL Server 2012**, clique em **Data Quality Services**e, em seguida, clique em **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="8090c-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="8090c-106">Na caixa de diálogo **conectar ao servidor** , selecione a instância do servidor de banco de dados na qual o DQS está instalado e clique em **conectar**.</span><span class="sxs-lookup"><span data-stu-id="8090c-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="8090c-107">![Caixa de diálogo conectar ao servidor](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Caixa de diálogo Conectar ao Servidor")</span><span class="sxs-lookup"><span data-stu-id="8090c-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="8090c-108">No Data Quality Client home page, no painel **Gerenciamento da base de dados de conhecimento** , clique em **nova base de dados de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="8090c-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="8090c-109">![Gerenciamento da Base de Dados de Conhecimento - Novo KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Gerenciamento da Base de Dados de Conhecimento - Novo KB")</span><span class="sxs-lookup"><span data-stu-id="8090c-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="8090c-110">Insira **fornecedores** para o **nome** da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="8090c-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="8090c-111">![Nova Base de Dados de Conhecimento - Gerenciamento de Domínio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Nova Base de Dados de Conhecimento - Gerenciamento de Domínio")</span><span class="sxs-lookup"><span data-stu-id="8090c-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="8090c-112">Confirme se **Criar base de dados de conhecimento de** campo está definido como **nenhum** , pois você está criando a base de dados de conhecimento dos **fornecedores** do zero.</span><span class="sxs-lookup"><span data-stu-id="8090c-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="8090c-113">Confirme se **Gerenciamento de domínio** está selecionado para a **atividade** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8090c-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="8090c-114">A atividade Gerenciamento de Domínio permite criar e gerenciar domínios da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="8090c-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="8090c-115">Na janela **Gerenciamento de domínio** , clique no botão da barra de ferramentas **criar um domínio** para criar um domínio.</span><span class="sxs-lookup"><span data-stu-id="8090c-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="8090c-116">![Botão de barra de ferramentas Criar Domínio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Botão de barra de ferramentas Criar Domínio")</span><span class="sxs-lookup"><span data-stu-id="8090c-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="8090c-117">Na caixa de diálogo **criar domínio** , digite **ID do fornecedor** para o **nome de domínio**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8090c-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="8090c-118">![Caixa de diálogo Criar Domínio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Caixa de diálogo Criar Domínio")</span><span class="sxs-lookup"><span data-stu-id="8090c-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="8090c-119">Repita a etapa anterior para criar os domínios a seguir com todas as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="8090c-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="8090c-120">Para manter o tutorial simples, você define o **tipo de dados** de todos os domínios como **cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="8090c-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="8090c-121">Os outros tipos de dados permitidos são: Inteiro, Decimal e Data.</span><span class="sxs-lookup"><span data-stu-id="8090c-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="8090c-122">Quando a opção **usar valores principais** é selecionada (padrão), todos os sinônimos são substituídos pelo valor principal do grupo de sinônimos na saída.</span><span class="sxs-lookup"><span data-stu-id="8090c-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="8090c-123">A configuração da opção **normalizar cadeia de caracteres** (padrão) remove quaisquer caracteres especiais nos valores de domínio.</span><span class="sxs-lookup"><span data-stu-id="8090c-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="8090c-124">A opção **Formatar saída para** permite selecionar a formatação que é aplicada quando os valores de dados no domínio são gerados.</span><span class="sxs-lookup"><span data-stu-id="8090c-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="8090c-125">Selecione **habilitar verificador ortográfico** (padrão) para executar o verificador ortográfico em todos os valores de cadeia de caracteres ao popular o domínio.</span><span class="sxs-lookup"><span data-stu-id="8090c-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="8090c-126">A configuração de **idioma** especifica qual versão de idioma do **Verificador ortográfico** você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="8090c-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="8090c-127">Selecione **desabilitar algoritmos de erro de sintaxe** para popular o domínio sem verificar valores de cadeia de caracteres para erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="8090c-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="8090c-128">Consulte o tópico [criar um domínio](https://msdn.microsoft.com/library/hh510401.aspx) na biblioteca MSDN para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8090c-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="8090c-129">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="8090c-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="8090c-130">Email de contato</span><span class="sxs-lookup"><span data-stu-id="8090c-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="8090c-131">Linha de Endereço</span><span class="sxs-lookup"><span data-stu-id="8090c-131">Address Line</span></span>  
  
    -   <span data-ttu-id="8090c-132">City</span><span class="sxs-lookup"><span data-stu-id="8090c-132">City</span></span>  
  
    -   <span data-ttu-id="8090c-133">Estado</span><span class="sxs-lookup"><span data-stu-id="8090c-133">State</span></span>  
  
    -   <span data-ttu-id="8090c-134">País</span><span class="sxs-lookup"><span data-stu-id="8090c-134">Country</span></span>  
  
    -   <span data-ttu-id="8090c-135">Zip</span><span class="sxs-lookup"><span data-stu-id="8090c-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8090c-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8090c-136">Next Step</span></span>  
 [<span data-ttu-id="8090c-137">Tarefa 2: Adicionando valores de domínio manualmente</span><span class="sxs-lookup"><span data-stu-id="8090c-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  
