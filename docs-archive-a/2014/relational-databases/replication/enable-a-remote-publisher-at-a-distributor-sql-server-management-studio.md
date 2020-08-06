---
title: Habilitar um Publicador remoto em um Distribuidor (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569910"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="d4d85-102">Habilitar um Publicador remoto em um Distribuidor (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d4d85-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d4d85-103">Habilite um Publicador a usar um Distribuidor remoto na página **Publicadores** .</span><span class="sxs-lookup"><span data-stu-id="d4d85-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="d4d85-104">Esta página está disponível no Assistente para Configurar Distribuição e na caixa de diálogo **Propriedades de Distribuidor – \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="d4d85-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="d4d85-105">Para mais informações sobre como usar o assistente e acessar a caixa de diálogo, consulte [Configurar publicação e distribuição](configure-publishing-and-distribution.md) e [Exibir e modificar o distribuidor e as propriedades do publicador](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4d85-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="d4d85-106">Para habilitar um Publicador no Assistente para Configurar Distribuição</span><span class="sxs-lookup"><span data-stu-id="d4d85-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="d4d85-107">Na página **Publicadores** do Assistente para Configurar Distribuição, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="d4d85-108">Clique em **Adicionar Editor SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="d4d85-109">Para obter informações sobre como habilitar um Oracle Publisher para usar um Distribuidor, consulte [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="d4d85-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="d4d85-110">Na caixa de diálogo **Conectar ao Servidor** , especifique a informação de conexão para o Publicador que usará o Distribuidor remoto e, então, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="d4d85-111">Na página **Senha do Distribuidor** nas caixas de texto **Senha** e **Confirmar Senha** , especifique uma senha forte para a conta **distributor_admin** , que a replicação usa para conectar-se do Publicador para o Distribuidor para executar tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d4d85-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="d4d85-112">Para exibir e modificar as configurações para um Publicador, clique no botão de propriedades ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="d4d85-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="d4d85-113">Para habilitar um Publicador na caixa de diálogo Propriedades de Distribuidor</span><span class="sxs-lookup"><span data-stu-id="d4d85-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="d4d85-114">Na página **Publicadores** da caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="d4d85-115">Clique em **Adicionar Editor SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="d4d85-116">Para obter informações sobre como habilitar um Oracle Publisher para usar um Distribuidor, consulte [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="d4d85-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="d4d85-117">Na caixa de diálogo **Conectar ao Servidor** , especifique a informação de conexão para o Publicador que usará o Distribuidor remoto e, então, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d4d85-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="d4d85-118">Na página **Publicadores** nas caixas de texto **Senha** e **Confirmar Senha** , especifique uma senha forte para a conta **distributor_admin** , que a replicação usará para conectar-se do Publicador para o Distribuidor para executar tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d4d85-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="d4d85-119">Para exibir e modificar as configurações para um Publicador, clique no botão de propriedades ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="d4d85-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4d85-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4d85-120">See Also</span></span>  
 <span data-ttu-id="d4d85-121">[Configurar a publicação e a distribuição](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="d4d85-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="d4d85-122">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="d4d85-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="d4d85-123">Proteger o Distribuidor</span><span class="sxs-lookup"><span data-stu-id="d4d85-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
