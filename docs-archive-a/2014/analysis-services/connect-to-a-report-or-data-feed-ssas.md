---
title: Conectar-se a um relatório ou feed de dados (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571016"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="b95f5-102">Conectar a um relatório ou feed de dados (SSAS)</span><span class="sxs-lookup"><span data-stu-id="b95f5-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="b95f5-103">Esta página do **Assistente de Importação de Tabela** permite que você se conecte a um feed de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="b95f5-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b95f5-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="b95f5-105">De um relatório</span><span class="sxs-lookup"><span data-stu-id="b95f5-105">From a Report</span></span>  
 <span data-ttu-id="b95f5-106">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="b95f5-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="b95f5-107">Digite um nome amigável para a conexão de feed de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="b95f5-108">**Caminho do Relatório**</span><span class="sxs-lookup"><span data-stu-id="b95f5-108">**Report Path**</span></span>  
 <span data-ttu-id="b95f5-109">Lista a URL para um relatório do SQL Server Reporting Services que gera feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="b95f5-110">Clique em **Procurar** para especificar a URL para o relatório.</span><span class="sxs-lookup"><span data-stu-id="b95f5-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="b95f5-111">Clique em **Exibir Relatório** para exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="b95f5-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="b95f5-112">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="b95f5-112">**Browse**</span></span>  
 <span data-ttu-id="b95f5-113">Navegue até um local onde um relatório está disponível.</span><span class="sxs-lookup"><span data-stu-id="b95f5-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="b95f5-114">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="b95f5-114">**Advanced**</span></span>  
 <span data-ttu-id="b95f5-115">Defina propriedades de conexão adicionais usando a caixa de diálogo **definir propriedades avançadas** .</span><span class="sxs-lookup"><span data-stu-id="b95f5-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="b95f5-116">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="b95f5-116">**Test Connection**</span></span>  
 <span data-ttu-id="b95f5-117">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="b95f5-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="b95f5-118">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="b95f5-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="b95f5-119">De um conjunto de dados do Azure DataMarket</span><span class="sxs-lookup"><span data-stu-id="b95f5-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="b95f5-120">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="b95f5-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="b95f5-121">Digite um nome amigável para a conexão de feed de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="b95f5-122">**URL do Feed de Dados**</span><span class="sxs-lookup"><span data-stu-id="b95f5-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="b95f5-123">Digite o caminho completo para um documento do serviço Atom (.atomsvc, .atom) ou a URL de um único feed de dados, ou clique em **Procurar** para selecionar um documento do serviço Atom.</span><span class="sxs-lookup"><span data-stu-id="b95f5-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="b95f5-124">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="b95f5-124">**Browse**</span></span>  
 <span data-ttu-id="b95f5-125">Navegue até um local onde um relatório está disponível.</span><span class="sxs-lookup"><span data-stu-id="b95f5-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="b95f5-126">Clique em **Exibir conjuntos de dados Azure DataMarket disponíveis** para exibir conjuntos de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b95f5-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="b95f5-127">**Chave de conta**</span><span class="sxs-lookup"><span data-stu-id="b95f5-127">**Account key**</span></span>  
 <span data-ttu-id="b95f5-128">Especifique a chave de conta usada para acessar suas assinaturas de conjunto de soluções do Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="b95f5-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="b95f5-129">**Considerar**</span><span class="sxs-lookup"><span data-stu-id="b95f5-129">**Find**</span></span>  
 <span data-ttu-id="b95f5-130">Localize uma chave de conta associada a uma conta do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="b95f5-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="b95f5-131">**Salvar minha chave de conta**</span><span class="sxs-lookup"><span data-stu-id="b95f5-131">**Save my account key**</span></span>  
 <span data-ttu-id="b95f5-132">Salva a chave de conta (criptografada) com a conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="b95f5-133">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="b95f5-133">**Advanced**</span></span>  
 <span data-ttu-id="b95f5-134">Defina propriedades de conexão adicionais usando a caixa de diálogo **definir propriedades avançadas** .</span><span class="sxs-lookup"><span data-stu-id="b95f5-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="b95f5-135">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="b95f5-135">**Test Connection**</span></span>  
 <span data-ttu-id="b95f5-136">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="b95f5-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="b95f5-137">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="b95f5-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="b95f5-138">De outros feeds</span><span class="sxs-lookup"><span data-stu-id="b95f5-138">From Other Feeds</span></span>  
 <span data-ttu-id="b95f5-139">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="b95f5-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="b95f5-140">Digite um nome amigável para a conexão de feed de dados.</span><span class="sxs-lookup"><span data-stu-id="b95f5-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="b95f5-141">**URL do Feed de Dados**</span><span class="sxs-lookup"><span data-stu-id="b95f5-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="b95f5-142">Digite o caminho completo para um documento do serviço Atom (.atomsvc, .atom) ou a URL de um único feed de dados, ou clique em **Procurar** para selecionar um documento do serviço Atom.</span><span class="sxs-lookup"><span data-stu-id="b95f5-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="b95f5-143">Clique em **Incluir todas as colunas de feed** para especificar se todas as colunas de feeds de dados serão importadas.</span><span class="sxs-lookup"><span data-stu-id="b95f5-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="b95f5-144">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="b95f5-144">**Browse**</span></span>  
 <span data-ttu-id="b95f5-145">Navegue até um local onde um feed de dados está disponível.</span><span class="sxs-lookup"><span data-stu-id="b95f5-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="b95f5-146">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="b95f5-146">**Advanced**</span></span>  
 <span data-ttu-id="b95f5-147">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="b95f5-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="b95f5-148">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="b95f5-148">**Test Connection**</span></span>  
 <span data-ttu-id="b95f5-149">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="b95f5-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="b95f5-150">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="b95f5-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
