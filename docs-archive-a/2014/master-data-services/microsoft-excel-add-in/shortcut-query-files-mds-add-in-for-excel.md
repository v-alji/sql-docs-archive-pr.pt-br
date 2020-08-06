---
title: Arquivos de consulta de atalho (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680010"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="677cd-102">Arquivos de consulta de atalho (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="677cd-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="677cd-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use arquivos de consulta de atalho para conectar e carregar dados usados frequentemente de forma rápida.</span><span class="sxs-lookup"><span data-stu-id="677cd-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="677cd-104">Você também pode usá-los quando desejar compartilhar dados do MDS com outros usuários.</span><span class="sxs-lookup"><span data-stu-id="677cd-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="677cd-105">Em vez de salvar a planilha e enviá-la por email, você deve salvar um arquivo de consulta de atalho e enviá-lo por email.</span><span class="sxs-lookup"><span data-stu-id="677cd-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="677cd-106">Isso garante que vocês se conectem ao repositório do MDS para obter os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="677cd-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="677cd-107">Arquivos de consulta de atalho são arquivos XML que contêm informações sobre:</span><span class="sxs-lookup"><span data-stu-id="677cd-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="677cd-108">A conexão ao repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="677cd-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="677cd-109">O modelo, a versão e a entidade.</span><span class="sxs-lookup"><span data-stu-id="677cd-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="677cd-110">Qualquer filtro aplicado quando o atalho foi criado.</span><span class="sxs-lookup"><span data-stu-id="677cd-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="677cd-111">A ordem da esquerda para a direita das colunas quando o atalho foi criado.</span><span class="sxs-lookup"><span data-stu-id="677cd-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="677cd-112">Você pode salvar esses arquivos em uma lista e escolher entre eles quando abrir o suplemento.</span><span class="sxs-lookup"><span data-stu-id="677cd-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="677cd-113">Você pode exportá-los para o seu computador ou para um local compartilhado, ou pode enviá-los a outros usuários por email.</span><span class="sxs-lookup"><span data-stu-id="677cd-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="677cd-114">Aplicativo QueryOpener</span><span class="sxs-lookup"><span data-stu-id="677cd-114">QueryOpener Application</span></span>  
 <span data-ttu-id="677cd-115">Todos os usuários que instalam o [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] têm um aplicativo chamado QueryOpener instalado.</span><span class="sxs-lookup"><span data-stu-id="677cd-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="677cd-116">Esse aplicativo é usado para abrir arquivos de consulta de atalho no [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="677cd-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="677cd-117">Se você clicar duas vezes em um arquivo de consulta de atalho, esse aplicativo será usado para abrir o arquivo automaticamente no suplemento.</span><span class="sxs-lookup"><span data-stu-id="677cd-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="677cd-118">Ao abrir um arquivo de consulta de atalho com esse aplicativo, você será solicitado tornar a conexão "segura", que o significa que você confia no conteúdo dessa localização.</span><span class="sxs-lookup"><span data-stu-id="677cd-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="677cd-119">Sempre que você marca uma conexão como segura, ela é adicionada a uma lista.</span><span class="sxs-lookup"><span data-stu-id="677cd-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="677cd-120">Se desejar apagar essa lista, abra a caixa de diálogo **Configurações** e, na seção **Servidores Adicionados à Lista Segura** , clique em **Desmarcar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="677cd-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="677cd-121">O local padrão para o aplicativo é *drive*: \Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="677cd-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="677cd-122">Há duas maneiras de abrir arquivos de consulta de atalho: você pode importá-los ou clicar duas vezes neles para abri-los automaticamente.</span><span class="sxs-lookup"><span data-stu-id="677cd-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="677cd-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="677cd-123">Related Tasks</span></span>  
  
|<span data-ttu-id="677cd-124">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="677cd-124">Task Description</span></span>|<span data-ttu-id="677cd-125">Tópico</span><span class="sxs-lookup"><span data-stu-id="677cd-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="677cd-126">Salve o conteúdo da planilha ativa como um arquivo de consulta de atalho.</span><span class="sxs-lookup"><span data-stu-id="677cd-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="677cd-127">Salvar um arquivo de consulta de atalho &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="677cd-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="677cd-128">Salve o arquivo de consulta de atalho que representa o conteúdo da planilha ativa.</span><span class="sxs-lookup"><span data-stu-id="677cd-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="677cd-129">Enviar um arquivo de consulta de atalho por email &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="677cd-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="677cd-130">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="677cd-130">Related Content</span></span>  
  
-   [<span data-ttu-id="677cd-131">Conexões &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="677cd-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="677cd-132">Suplemento do Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="677cd-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="677cd-133">Segurança &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="677cd-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
