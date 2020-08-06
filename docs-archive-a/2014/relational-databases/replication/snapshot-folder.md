---
title: Pasta de instantâneo | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583483"
---
# <a name="snapshot-folder"></a><span data-ttu-id="c3e2e-102">Pasta do Instantâneo</span><span class="sxs-lookup"><span data-stu-id="c3e2e-102">Snapshot Folder</span></span>
  <span data-ttu-id="c3e2e-103">A página **Pasta do Instantâneo** aparece no Assistente para Configurar a Distribuição e no Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="c3e2e-104">O local especificado para a pasta do instantâneo será usado como padrão para todos os Publicadores habilitados nesse assistente (a pasta de instantâneo padrão não se aplica a Publicadores posteriormente habilitados usando a caixa de diálogo **Propriedades do Distribuidor** ).</span><span class="sxs-lookup"><span data-stu-id="c3e2e-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="c3e2e-105">Você pode substituir esse padrão por qualquer Publicador na página **Publicadores** do Assistente para Configurar a Distribuição da caixa de diálogo **Propriedades do Distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="c3e2e-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="c3e2e-106">A pasta de instantâneo é simplesmente um diretório que você designou como um compartilhamento, agentes que leem essa pasta e gravam nela devem ter permissões suficientes para acessá-la.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="c3e2e-107">Para obter mais informações sobre como proteger a pasta adequadamente, consulte [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md) (Proteger a pasta de instantâneo).</span><span class="sxs-lookup"><span data-stu-id="c3e2e-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="c3e2e-108">Antes de implementar replicação, teste se os agentes de replicação poderão se conectar à pasta de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="c3e2e-109">Faça logon na conta que será usada por cada agente e depois tente acessar a pasta de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3e2e-110">Opções</span><span class="sxs-lookup"><span data-stu-id="c3e2e-110">Options</span></span>  
 <span data-ttu-id="c3e2e-111">**Pasta do instantâneo**</span><span class="sxs-lookup"><span data-stu-id="c3e2e-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="c3e2e-112">Insira o caminho para a pasta onde você quer arquivos de instantâneo sejam armazenados.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3e2e-113">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que você use um compartilhamento de rede como um local de pasta de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="c3e2e-114">Caminhos locais (os que iniciam com uma letra da unidade, como C:\\) não são acessíveis a agentes em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="c3e2e-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e2e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3e2e-115">See Also</span></span>  
 <span data-ttu-id="c3e2e-116">[Locais de pastas de instantâneos alternativos](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="c3e2e-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="c3e2e-117">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c3e2e-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="c3e2e-118">[Configurar a publicação e a distribuição](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c3e2e-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="c3e2e-119">[Exibir e modificar propriedades de Publicador e Distribuidor](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c3e2e-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="c3e2e-120">Inicializar uma assinatura com um instantâneo</span><span class="sxs-lookup"><span data-stu-id="c3e2e-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
