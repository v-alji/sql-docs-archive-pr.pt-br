---
title: Publicador Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569354"
---
# <a name="oracle-publisher"></a><span data-ttu-id="a13c1-102">Editor Oracle</span><span class="sxs-lookup"><span data-stu-id="a13c1-102">Oracle Publisher</span></span>
  <span data-ttu-id="a13c1-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] em diante, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite que você publique dados de um Oracle Database usando a replicação de instantâneo e transacional.</span><span class="sxs-lookup"><span data-stu-id="a13c1-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="a13c1-104">Para obter mais informações, consulte [Visão geral da publicação Oracle](non-sql/oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a13c1-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="a13c1-105">O Editor Oracle deve usar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor remoto; esse assistente deve ser executado no servidor depois que o software de rede Oracle necessário tiver sido instalado e testado.</span><span class="sxs-lookup"><span data-stu-id="a13c1-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="a13c1-106">Para obter mais informações, consulte [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md) (Configurar um publicador do Oracle).</span><span class="sxs-lookup"><span data-stu-id="a13c1-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a13c1-107">Se outro administrador tiver configurado o banco de dados Oracle como um Publicador, depois de clicar em **Avançar** você será solicitado a inserir a senha do logon de replicação usado para conectar-se ao banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="a13c1-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> <span data-ttu-id="a13c1-108">O[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criará um mapeamento entre seu logon e a conexão de servidor vinculado com o banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="a13c1-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="a13c1-109">Você não será solicitado a inserir uma senha para conexões subsequentes com o banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="a13c1-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a13c1-110">Opções</span><span class="sxs-lookup"><span data-stu-id="a13c1-110">Options</span></span>  
 <span data-ttu-id="a13c1-111">**Publicadores Oracle**</span><span class="sxs-lookup"><span data-stu-id="a13c1-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="a13c1-112">Selecione um Editor Oracle na lista.</span><span class="sxs-lookup"><span data-stu-id="a13c1-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="a13c1-113">Essa lista contém Editores Oracle que foram previamente configurados para usar o servidor no qual o assistente está sendo executado como Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a13c1-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="a13c1-114">Se a lista estiver vazia ou o Editor Oracle que você quiser usar não estiver na lista, clique em **Adicionar Editor Oracle**.</span><span class="sxs-lookup"><span data-stu-id="a13c1-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="a13c1-115">**Adicionar Editor Oracle**</span><span class="sxs-lookup"><span data-stu-id="a13c1-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="a13c1-116">Clique para iniciar a caixa de diálogo **Propriedades do Distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="a13c1-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="a13c1-117">Nessa caixa de diálogo, clique em **Adicionar**e em **Adicionar Editor Oracle**.</span><span class="sxs-lookup"><span data-stu-id="a13c1-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="a13c1-118">Na caixa de diálogo **Conectar ao Servidor** , especifique o nome do servidor Oracle, o logon e a senha para o esquema de usuário administrativo de replicação.</span><span class="sxs-lookup"><span data-stu-id="a13c1-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="a13c1-119">Para obter mais informações, consulte [Conectar ao servidor &#40;Oracle&#41;, Logon](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="a13c1-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a13c1-120">Se o servidor no qual o assistente está sendo executado ainda não estiver configurado como Distribuidor, você será solicitado a configurá-lo agora.</span><span class="sxs-lookup"><span data-stu-id="a13c1-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13c1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a13c1-121">See Also</span></span>  
 [<span data-ttu-id="a13c1-122">Criar uma publicação de um Banco de Dados Oracle</span><span class="sxs-lookup"><span data-stu-id="a13c1-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
