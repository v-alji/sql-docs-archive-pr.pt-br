---
title: Arquivos de banco de dados de origem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685817"
---
# <a name="source-database-files"></a><span data-ttu-id="a773c-102">Arquivos de banco de dados de origem</span><span class="sxs-lookup"><span data-stu-id="a773c-102">Source database files</span></span>
  <span data-ttu-id="a773c-103">Use a caixa de diálogo **Arquivos de Banco de Dados de Origem** para visualizar os nomes e locais do arquivo do banco de dados no servidor de origem ou especificar um local de compartilhamento de arquivos na rede para a tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a773c-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="a773c-104">Para obter mais informações sobre essa tarefa, consulte [Tarefa Transferir Banco de Dados](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="a773c-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="a773c-105">Para popular esta caixa de diálogo com os nomes e locais dos arquivos do banco de dados no servidor de origem, especifique primeiro **SourceConnection** e **SourceDatabaseName** na página **Banco de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="a773c-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a773c-106">Opções</span><span class="sxs-lookup"><span data-stu-id="a773c-106">Options</span></span>  
 <span data-ttu-id="a773c-107">**Arquivo de Origem**</span><span class="sxs-lookup"><span data-stu-id="a773c-107">**Source File**</span></span>  
 <span data-ttu-id="a773c-108">Nomes do arquivo de banco de dados no servidor de origem que serão transferidos.</span><span class="sxs-lookup"><span data-stu-id="a773c-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="a773c-109">O**Arquivo de Origem** é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a773c-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="a773c-110">**Pasta de Origem**</span><span class="sxs-lookup"><span data-stu-id="a773c-110">**Source Folder**</span></span>  
 <span data-ttu-id="a773c-111">Pasta no servidor de origem em que residem os arquivos de banco de dados a serem transferidos.</span><span class="sxs-lookup"><span data-stu-id="a773c-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="a773c-112">A**Pasta de Origem** é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a773c-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="a773c-113">**Compartilhamento de Arquivos na Rede**</span><span class="sxs-lookup"><span data-stu-id="a773c-113">**Network File Share**</span></span>  
 <span data-ttu-id="a773c-114">Pasta de compartilhamento de rede no servidor de origem da qual os arquivos de banco de dados serão transferidos.</span><span class="sxs-lookup"><span data-stu-id="a773c-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="a773c-115">Use **Compartilhamento de Arquivo na Rede** ao transferir um banco de dados em modo offline, especificando **DatabaseOffline** em **Método** na página **Banco de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="a773c-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="a773c-116">Insira a localização de compartilhamento de arquivos na rede ou clique no botão Procurar **(...)** para localizá-la.</span><span class="sxs-lookup"><span data-stu-id="a773c-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="a773c-117">Na transferência de um banco de dados em modo offline, os arquivos de banco de dados são copiados para o local **Compartilhamento de arquivo na rede** no servidor de origem, antes de serem transferidos ao servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a773c-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a773c-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a773c-118">See Also</span></span>  
 <span data-ttu-id="a773c-119">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a773c-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a773c-120">[Editor da tarefa Transferir Banco de dados &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a773c-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="a773c-121">Editor da Tarefa Transferir Banco de Dados &#40;Página Bancos de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="a773c-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
