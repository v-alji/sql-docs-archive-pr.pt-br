---
title: Reparar uma instalação do Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576147"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="466a7-102">Reparar uma instalação do Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="466a7-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="466a7-103">A reparação de um componente do Distributed Replay (controlador ou cliente) fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="466a7-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="466a7-104">Instalará todos os arquivos associados em disco novamente e substituirá os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="466a7-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="466a7-105">Recriará a conta de serviço do Windows se a conta de serviço correspondente for removida.</span><span class="sxs-lookup"><span data-stu-id="466a7-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="466a7-106">Você não pode usar a operação Reparar para adicionar ou remover componentes.</span><span class="sxs-lookup"><span data-stu-id="466a7-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="466a7-107">Para adicionar ou remover componentes, marque ou desmarque o componente correspondente na árvore de Recurso na página **Seleção de Recurso** na Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="466a7-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="466a7-108">Para reparar uma instalação com falha do Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="466a7-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="466a7-109">No menu **Iniciar** , clique em **Painel de Controle**e clique duas vezes em **Adicionar ou Remover Programas**.</span><span class="sxs-lookup"><span data-stu-id="466a7-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="466a7-110">Selecione [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] na janela **Desinstalar ou alterar um programa** e, na caixa de diálogo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , clique em **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="466a7-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="466a7-111">Siga as etapas no assistente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e, na página **Selecionar Recursos** , selecione os componentes do Distributed Replay que você deseja reparar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="466a7-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="466a7-112">Conclua o Assistente de Instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para reparar os recursos selecionados de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="466a7-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
