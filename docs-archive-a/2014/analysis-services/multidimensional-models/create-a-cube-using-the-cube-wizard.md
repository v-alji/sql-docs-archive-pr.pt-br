---
title: Criar um cubo usando o assistente para cubos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683786"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="19854-102">Criar um cubo usando o Assistente para Cubos</span><span class="sxs-lookup"><span data-stu-id="19854-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="19854-103">Você pode criar um novo cubo usando o Assistente para Cubos do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19854-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="19854-104">Para criar um novo cubo</span><span class="sxs-lookup"><span data-stu-id="19854-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="19854-105">No **Gerenciador de Soluções**, clique com o botão direito do mouse em **Cubos**e clique em **Novo Cubo**.</span><span class="sxs-lookup"><span data-stu-id="19854-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="19854-106">Na página **Selecionar Método de Criação** do Assistente para Cubos, selecione **Usar tabelas existentes**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19854-107">Ocasionalmente pode ser necessário criar um cubo sem usar as tabelas existentes.</span><span class="sxs-lookup"><span data-stu-id="19854-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="19854-108">Para criar um cubo vazio, selecione **Criar um cubo vazio**.</span><span class="sxs-lookup"><span data-stu-id="19854-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="19854-109">Para gerar tabelas, selecione **Gerar tabelas na fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="19854-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="19854-110">Na página **Selecionar Tabelas de Grupos de Medidas** , execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="19854-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="19854-111">Na lista **Exibição da fonte de dados** , selecione uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="19854-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="19854-112">Na lista **Tabelas de grupos de medidas** , selecione as tabelas que serão usadas para criar grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="19854-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="19854-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="19854-114">Na página **Selecionar Medidas** , selecione as medidas que você quer incluir no cubo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="19854-115">Opcionalmente, você pode alterar os nomes das medidas e grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="19854-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="19854-116">Na página **Selecionar Dimensões Existentes** , selecione as dimensões existentes a serem incluídas no cubo e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19854-117">A página **Selecionar Dimensões Existentes** será exibida se existirem dimensões no banco de dados para qualquer um dos grupos de medidas selecionados.</span><span class="sxs-lookup"><span data-stu-id="19854-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="19854-118">Na página **Selecionar Novas Dimensões** , selecione as dimensões novas para criar e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19854-119">A página **Selecionar Novas Dimensões** será exibida se alguma tabela for boa candidata para a tabela de dimensão e se as tabelas ainda não tiverem sido usadas pelas dimensões existentes.</span><span class="sxs-lookup"><span data-stu-id="19854-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="19854-120">Na página **Selecionar Chaves de Dimensão Ausentes** , selecione uma chave para a dimensão e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19854-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19854-121">A página **Selecionar Chaves de Dimensão Ausentes** será exibida se as tabelas de dimensão especificadas não tiverem uma chave definida.</span><span class="sxs-lookup"><span data-stu-id="19854-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="19854-122">Na página **Concluindo o Assistente** , digite um nome para o novo cubo e examine a estrutura do cubo.</span><span class="sxs-lookup"><span data-stu-id="19854-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="19854-123">Se você quiser fazer mudanças, clique em **Voltar**; caso contrário, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="19854-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19854-124">Você pode usar o Designer de Cubo para configurar o cubo após concluir o Assistente para Cubos.</span><span class="sxs-lookup"><span data-stu-id="19854-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="19854-125">Você pode usar o Designer de Dimensão para adicionar, remover e configurar atributos e hierarquias nas dimensões criadas.</span><span class="sxs-lookup"><span data-stu-id="19854-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
