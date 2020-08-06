---
title: Criar credencial – autenticar no Armazenamento do Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684778"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="cbac1-102">Criar credencial - autenticar no Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="cbac1-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="cbac1-103">Use a caixa de diálogo **Backup para URL – Criar Credencial** para criar uma nova Credencial do SQL.</span><span class="sxs-lookup"><span data-stu-id="cbac1-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="cbac1-104">Ao usar essa caixa de diálogo para criar uma credencial, você precisa fornecer um Certificado de Gerenciamento do Azure adicionado ao repositório de certificados local ou a um perfil de publicação baixado em seu computador para validar a assinatura e as informações de conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="cbac1-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="cbac1-105">**CREDENCIAL DO SQL**</span><span class="sxs-lookup"><span data-stu-id="cbac1-105">**SQL Credential**</span></span>  
 <span data-ttu-id="cbac1-106">Especifica o nome da Credencial do SQL que você quer criar.</span><span class="sxs-lookup"><span data-stu-id="cbac1-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="cbac1-107">Credenciais do Azure</span><span class="sxs-lookup"><span data-stu-id="cbac1-107">Azure Credentials</span></span>  
 <span data-ttu-id="cbac1-108">**Certificado de Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="cbac1-108">**Management Certificate**</span></span>  
 <span data-ttu-id="cbac1-109">Use essa opção para especificar um certificado do repositório de certificados local que corresponda ao certificado de gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cbac1-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="cbac1-110">Para obter mais informações sobre o certificado de gerenciamento do Azure, confira [Criar e carregar um certificado de gerenciamento para o Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span><span class="sxs-lookup"><span data-stu-id="cbac1-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="cbac1-111">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="cbac1-111">**Subscription**</span></span>  
 <span data-ttu-id="cbac1-112">Selecione, digite ou cole a ID de assinatura do Azure que corresponde ao certificado de gerenciamento do repositório local de certificados.</span><span class="sxs-lookup"><span data-stu-id="cbac1-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="cbac1-113">**Perfil de Publicação**</span><span class="sxs-lookup"><span data-stu-id="cbac1-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="cbac1-114">Use essa opção se você tiver um perfil de publicação baixado no seu computador.</span><span class="sxs-lookup"><span data-stu-id="cbac1-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="cbac1-115">Se você usar essa opção, a ID da assinatura e o certificado serão automaticamente populados.</span><span class="sxs-lookup"><span data-stu-id="cbac1-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cbac1-116">No momento, o SQL Server oferece suporte à versão do perfil de publicação 2.0.</span><span class="sxs-lookup"><span data-stu-id="cbac1-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="cbac1-117">Para baixar a versão com suporte do perfil de publicação, consulte [Download do perfil de publicação 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="cbac1-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="cbac1-118">Conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="cbac1-118">Storage Account</span></span>  
 <span data-ttu-id="cbac1-119">Selecione a conta de armazenamento que você deseja usar para armazenar os arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="cbac1-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
