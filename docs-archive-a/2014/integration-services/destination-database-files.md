---
title: Arquivos de banco de dados de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582554"
---
# <a name="destination-database-files"></a><span data-ttu-id="5ac93-102">Arquivos de banco de dados de destino</span><span class="sxs-lookup"><span data-stu-id="5ac93-102">Destination Database Files</span></span>
  <span data-ttu-id="5ac93-103">Use a caixa de diálogo **Arquivos do Banco de Dados de Destino** para exibir ou alterar os nomes e locais dos arquivos de banco de dados no servidor de destino ou especificar um local de arquivos na rede para a tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="5ac93-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="5ac93-104">Para obter mais informações sobre essa tarefa, consulte [Tarefa Transferir Banco de Dados](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="5ac93-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="5ac93-105">Para popular automaticamente essa caixa de diálogo com os locais e nomes de arquivos no servidor de origem, especifique o **SourceConnection**, **SourceDatabaseName**, e **SourceDatabaseFiles** primeiro na página **Bancos de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="5ac93-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ac93-106">Opções</span><span class="sxs-lookup"><span data-stu-id="5ac93-106">Options</span></span>  
 <span data-ttu-id="5ac93-107">**Arquivo de Destino**</span><span class="sxs-lookup"><span data-stu-id="5ac93-107">**Destination File**</span></span>  
 <span data-ttu-id="5ac93-108">Nomes dos arquivos de banco de dados transferidos no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="5ac93-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="5ac93-109">Digite o nome do arquivo ou clique no nome do arquivo para editá-lo.</span><span class="sxs-lookup"><span data-stu-id="5ac93-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="5ac93-110">**Pasta de Destino**</span><span class="sxs-lookup"><span data-stu-id="5ac93-110">**Destination Folder**</span></span>  
 <span data-ttu-id="5ac93-111">Pasta no servidor de destino para onde os arquivos de banco de dados serão transferidos.</span><span class="sxs-lookup"><span data-stu-id="5ac93-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="5ac93-112">Digite o caminho da pasta, clique no caminho da pasta para editá-lo ou clique em procurar para localizar a pasta onde você quer transferir os arquivos de banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="5ac93-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="5ac93-113">**Compartilhamento de Arquivos na Rede**</span><span class="sxs-lookup"><span data-stu-id="5ac93-113">**Network File Share**</span></span>  
 <span data-ttu-id="5ac93-114">Pasta compartilhada de rede no servidor de destino para o qual os arquivos de banco de dados serão transferidos.</span><span class="sxs-lookup"><span data-stu-id="5ac93-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="5ac93-115">Use **Compartilhamento de arquivo na rede** ao transferir um banco de dados em modo offline, especificando **DatabaseOffline** em **Método** na página **Banco de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="5ac93-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="5ac93-116">Insira o local de compartilhamento de arquivos na rede ou clique em Procurar para localizá-lo.</span><span class="sxs-lookup"><span data-stu-id="5ac93-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="5ac93-117">Ao transferir um banco de dados em modo offline, os arquivos de banco de dados são copiados para o local **Compartilhamento de arquivo na rede** antes de serem transferidos para o local **Pasta de destino** .</span><span class="sxs-lookup"><span data-stu-id="5ac93-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac93-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ac93-118">See Also</span></span>  
 <span data-ttu-id="5ac93-119">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5ac93-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5ac93-120">[Editor da tarefa Transferir Banco de dados &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5ac93-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="5ac93-121">Editor da Tarefa Transferir Banco de Dados &#40;Página Bancos de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac93-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
