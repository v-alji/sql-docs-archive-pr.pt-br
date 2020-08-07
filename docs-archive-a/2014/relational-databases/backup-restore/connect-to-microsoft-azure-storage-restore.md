---
title: Conectar-se ao armazenamento do Azure (restaurar) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583660"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="4eef3-102">Conectar a um Armazenamento do Microsoft Azure (restaurar)</span><span class="sxs-lookup"><span data-stu-id="4eef3-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="4eef3-103">A caixa de diálogo permite que você especifique as informações da conexão com a conta de armazenamento do Azure a fim de recuperar o armazenamento de arquivos nessa conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="4eef3-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="4eef3-104">Depois de especificar as informações necessárias, clique em **Conectar** para estabelecer a conexão com o Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="4eef3-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="4eef3-105">Conta de Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="4eef3-105">Azure Storage Account</span></span>  
 <span data-ttu-id="4eef3-106">**Conta de armazenamento**</span><span class="sxs-lookup"><span data-stu-id="4eef3-106">**Storage account**</span></span>  
 <span data-ttu-id="4eef3-107">Selecione, digite ou cole o nome da conta de armazenamento do Azure que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="4eef3-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="4eef3-108">A caixa suspensa lista as contas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4eef3-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="4eef3-109">**Chave de conta**</span><span class="sxs-lookup"><span data-stu-id="4eef3-109">**Account key**</span></span>  
 <span data-ttu-id="4eef3-110">Especifique a chave de acesso da conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="4eef3-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="4eef3-111">Caixa de seleção**Usar pontos de extremidade seguros (HTTPS)**</span><span class="sxs-lookup"><span data-stu-id="4eef3-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="4eef3-112">Selecione esta opção para estabelecer uma conexão segura com o Armazenamento do Azure – recomendado.</span><span class="sxs-lookup"><span data-stu-id="4eef3-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="4eef3-113">Caixa de seleção**Salvar chave de conta**</span><span class="sxs-lookup"><span data-stu-id="4eef3-113">**Save account key** check box</span></span>  
 <span data-ttu-id="4eef3-114">Marque esta caixa de seleção se desejar que o SQL Server se lembre da chave de acesso para essa conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4eef3-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="4eef3-115">CREDENCIAL DO SQL</span><span class="sxs-lookup"><span data-stu-id="4eef3-115">SQL Credential</span></span>  
 <span data-ttu-id="4eef3-116">**Selecionar uma credencial existente**</span><span class="sxs-lookup"><span data-stu-id="4eef3-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="4eef3-117">Selecione uma credencial existente do SQL que corresponda à conta de armazenamento e às informações de chave de conta.</span><span class="sxs-lookup"><span data-stu-id="4eef3-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="4eef3-118">**Criar uma nova credencial**</span><span class="sxs-lookup"><span data-stu-id="4eef3-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="4eef3-119">Selecione esta opção para criar uma nova credencial usando a conta de armazenamento e as informações de chave de conta.</span><span class="sxs-lookup"><span data-stu-id="4eef3-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="4eef3-120">Especifique o nome da nova credencial no campo de **Nome da Credencial** .</span><span class="sxs-lookup"><span data-stu-id="4eef3-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
