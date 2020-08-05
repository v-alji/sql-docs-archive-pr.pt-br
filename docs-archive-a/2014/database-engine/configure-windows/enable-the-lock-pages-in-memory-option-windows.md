---
title: Habilitar a opção Bloquear Páginas na Memória (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574277"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="67469-102">Habilitar a opção Bloquear Páginas na Memória (Windows)</span><span class="sxs-lookup"><span data-stu-id="67469-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="67469-103">Essa política do Windows determina quais contas podem usar um processo para manter dados na memória física, impedindo o sistema de paginar os dados para a memória virtual em disco.</span><span class="sxs-lookup"><span data-stu-id="67469-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67469-104">O bloqueio de páginas na memória pode aumentar o desempenho quando se espera paginar a memória em disco.</span><span class="sxs-lookup"><span data-stu-id="67469-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="67469-105">Use a ferramenta Política de Grupo do Windows (gpedit.msc) para habilitar essa política para a conta usada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67469-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="67469-106">Você deve ser um administrador do sistema para alterar essa política.</span><span class="sxs-lookup"><span data-stu-id="67469-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="67469-107">Para habilitar a opção de bloqueio de páginas na memória</span><span class="sxs-lookup"><span data-stu-id="67469-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="67469-108">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="67469-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="67469-109">Na caixa **abrir** , digite `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="67469-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="67469-110">No console **Editor de Política de Grupo Local** , expanda **Configuração do Computador**e depois expanda **Configurações do Windows**.</span><span class="sxs-lookup"><span data-stu-id="67469-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="67469-111">Expanda **Configurações de Segurança**e então expanda **Políticas Locais**.</span><span class="sxs-lookup"><span data-stu-id="67469-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="67469-112">Selecione a pasta **Atribuição de direitos de usuários** .</span><span class="sxs-lookup"><span data-stu-id="67469-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="67469-113">As políticas serão exibidas no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="67469-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="67469-114">No painel, clique duas vezes em **Bloquear páginas na memória**.</span><span class="sxs-lookup"><span data-stu-id="67469-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="67469-115">Na caixa de diálogo **Configuração de Segurança Local – Bloquear páginas na memória**, clique em **Adicionar Usuário ou Grupo**.</span><span class="sxs-lookup"><span data-stu-id="67469-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="67469-116">Na caixa de diálogo **Selecionar Usuários, Contas de Serviço ou Grupos** , adicione uma conta com privilégios para executar sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="67469-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="67469-117">Faça logoff e depois faça logon para que essas alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="67469-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67469-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67469-118">See Also</span></span>  
 [<span data-ttu-id="67469-119">Opções Server Memory de configuração do servidor</span><span class="sxs-lookup"><span data-stu-id="67469-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
