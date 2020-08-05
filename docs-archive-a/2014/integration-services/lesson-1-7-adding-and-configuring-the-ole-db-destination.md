---
title: 'Etapa 7: Adicionando e configurando o destino OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574129"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="582ff-102">Etapa 7: Adicionar e configurar o destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="582ff-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="582ff-103">Seu pacote agora extrai dados de uma fonte de arquivo simples e transforma esses dados em um formato compatível com o destino.</span><span class="sxs-lookup"><span data-stu-id="582ff-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="582ff-104">A próxima tarefa é carregar os dados transformados no destino.</span><span class="sxs-lookup"><span data-stu-id="582ff-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="582ff-105">Para carregar os dados, você deve adicionar um destino OLE DB ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="582ff-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="582ff-106">O destino do OLE DB pode usar uma tabela, exibição de banco de dados ou um comando SQL para carregar os dados em uma diversidade de bancos de dados compatíveis com o OLE DB.</span><span class="sxs-lookup"><span data-stu-id="582ff-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="582ff-107">Neste procedimento, você adiciona e configura um destino OLE DB para usar o gerenciador de conexões OLE DB criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="582ff-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="582ff-108">Para adicionar e configurar a amostra de destino do OLE DB</span><span class="sxs-lookup"><span data-stu-id="582ff-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="582ff-109">Na **caixa de ferramentas do SSIS**, expanda **outros destinos**e arraste **OLE DB destino** até a superfície de design da guia **fluxo de dados** . Coloque o destino do OLE DB diretamente abaixo da transformação chave de **data de pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="582ff-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="582ff-110">Clique na transformação **Chave de Data de Pesquisa** e arraste a seta verde sobre o **Destino OLE DB** recém-adicionado para conectar os dois componentes.</span><span class="sxs-lookup"><span data-stu-id="582ff-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="582ff-111">Na caixa de diálogo **Seleção de Saída e Entrada** , na caixa de listagem **Saída** , clique em **Saída de Correspondência de Pesquisa**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="582ff-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="582ff-112">Na superfície de design de **Fluxo de Dados** , clique em **Destino OLE DB** , no componente **Destino de OLE DB** recém-adicionado e altere o nome para **Destino OLE DB de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="582ff-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="582ff-113">Clique duas vezes em **Destino OLE DB de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="582ff-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="582ff-114">Na caixa de diálogo **Editor de Destino do OLE DB** , verifique se **localhost.AdventureWorksDW2012** está selecionado na caixa **Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="582ff-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="582ff-115">Na caixa **Nome da tabela ou da exibição** , digite ou selecione **[dbo].[FactCurrencyRate]**.</span><span class="sxs-lookup"><span data-stu-id="582ff-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="582ff-116">Clique no botão **Novo** para criar uma nova tabela.</span><span class="sxs-lookup"><span data-stu-id="582ff-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="582ff-117">Altere o nome da tabela no script para **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="582ff-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="582ff-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="582ff-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="582ff-119">Depois de clicar em **OK**, a caixa de diálogo será fechada e o **Nome da tabela ou da exibição** será alterado automaticamente para **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="582ff-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="582ff-120">Clique em **Mapeamentos**.</span><span class="sxs-lookup"><span data-stu-id="582ff-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="582ff-121">Verifique se as colunas de entrada **AverageRate**, **CurrencyKey**, **EndOfDayRate**e **DateKey** estão mapeadas corretamente para as colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="582ff-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="582ff-122">Se forem mapeadas colunas com o mesmo nome, o mapeamento estará correto.</span><span class="sxs-lookup"><span data-stu-id="582ff-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="582ff-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="582ff-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="582ff-124">Clique com o botão direito do mouse no destino **Destino OLE DB de Exemplo** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="582ff-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="582ff-125">No janela Propriedades, verifique se a `LocaleID` propriedade está definida como **inglês (Estados Unidos)** e se a `DefaultCodePage` propriedade está definida como **1252**.</span><span class="sxs-lookup"><span data-stu-id="582ff-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="582ff-126">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="582ff-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="582ff-127">Etapa 8: Tornar o pacote da Lição 1 mais fácil de compreender</span><span class="sxs-lookup"><span data-stu-id="582ff-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="582ff-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="582ff-128">See Also</span></span>  
 [<span data-ttu-id="582ff-129">Destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="582ff-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  
