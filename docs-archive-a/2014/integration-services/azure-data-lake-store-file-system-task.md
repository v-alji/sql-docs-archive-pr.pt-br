---
title: Tarefa do sistema de arquivos do Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575300"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="5b077-102">Tarefa do sistema de arquivos do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="5b077-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="5b077-103">A **tarefa sistema de arquivos Azure data Lake Store** permite que os usuários executem várias operações de sistema de arquivos em [Azure data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span><span class="sxs-lookup"><span data-stu-id="5b077-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="5b077-104">Para adicionar uma tarefa do sistema de arquivos do Azure Data Lake Store para um pacote, arraste-o da Caixa de Ferramentas do SSIS para a tela do designer.</span><span class="sxs-lookup"><span data-stu-id="5b077-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="5b077-105">Em seguida, clique duas vezes na tarefa ou clique com o botão direito do mouse na tarefa e selecione **Editar**para abrir a caixa de diálogo editor da tarefa.</span><span class="sxs-lookup"><span data-stu-id="5b077-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="5b077-106">A propriedade **Operation** especifica a operação do sistema de arquivos a ser executada.</span><span class="sxs-lookup"><span data-stu-id="5b077-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="5b077-107">As operações a seguir têm suporte.</span><span class="sxs-lookup"><span data-stu-id="5b077-107">The following operations are supported.</span></span>

* <span data-ttu-id="5b077-108">**CopyToADLS:** carregar arquivos para o ADLS.</span><span class="sxs-lookup"><span data-stu-id="5b077-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="5b077-109">**CopyFromADLS:** baixar arquivos do ADLS.</span><span class="sxs-lookup"><span data-stu-id="5b077-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="5b077-110">Para qualquer operação, você precisa especificar um gerenciador de conexões do Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="5b077-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="5b077-111">Aqui estão as descrições das propriedades específicas de cada operação.</span><span class="sxs-lookup"><span data-stu-id="5b077-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="5b077-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="5b077-112">CopyToADLS</span></span>

* <span data-ttu-id="5b077-113">**LocalDirectory:** Especifica o diretório de origem que contém os arquivos a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="5b077-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="5b077-114">**FileNamePattern:** especifica um filtro de nome de arquivo para arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="5b077-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="5b077-115">Somente os arquivos cujo nome corresponde ao padrão especificado serão carregados.</span><span class="sxs-lookup"><span data-stu-id="5b077-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="5b077-116">Curingas `*` e `?` são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="5b077-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="5b077-117">**SearchRecursively:** especifica se deve-se pesquisar recursivamente dentro do diretório de origem por arquivos a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="5b077-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="5b077-118">**AzureDataLakeDirectory:** especifica o diretório de destino do ADLS para o qual carregar arquivos.</span><span class="sxs-lookup"><span data-stu-id="5b077-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="5b077-119">**Fileexpirey:** Especifica uma data e hora de expiração para os arquivos carregados em ADLS, ou deixe essa propriedade em branco para indicar que os arquivos nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="5b077-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="5b077-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="5b077-120">CopyFromADLS</span></span>

* <span data-ttu-id="5b077-121">**AzureDataLakeDirectory:** especifica o diretório de origem do ADLS que contém os arquivos a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="5b077-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="5b077-122">**SearchRecursively:** especifica se deve-se pesquisar recursivamente dentro do diretório de origem por arquivos a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="5b077-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="5b077-123">**LocalDirectory:** especifica o diretório de destino no qual armazenar arquivos baixados.</span><span class="sxs-lookup"><span data-stu-id="5b077-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
