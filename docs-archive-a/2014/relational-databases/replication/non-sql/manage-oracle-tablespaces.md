---
title: Gerenciar espaços para tabela Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681578"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="fe4c0-102">Gerenciar espaços de tabela Oracle</span><span class="sxs-lookup"><span data-stu-id="fe4c0-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="fe4c0-103">Um espaço de tabela é uma unidade de armazenamento de banco de dados que é aproximadamente equivalente a um grupo de arquivo no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe4c0-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fe4c0-104">Os espaços de tabela permitem armazenamento e gerenciamento de objetos de banco de dados dentro de grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="fe4c0-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="fe4c0-105">Para obter mais informações, consulte a documentação Oracle.</span><span class="sxs-lookup"><span data-stu-id="fe4c0-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="fe4c0-106">Ao configurar uma tabela como parte de uma publicação Oracle, você pode especificar opcionalmente um espaço de tabela do Oracle existente para ser usado ao armazenar informações de log de replicação.</span><span class="sxs-lookup"><span data-stu-id="fe4c0-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="fe4c0-107">Se não especificado, o espaço de tabela para os objetos de replicação é o espaço de tabela padrão associado com o esquema de usuário administrativo de replicação que foi configurado ao se configurar o Publicador.</span><span class="sxs-lookup"><span data-stu-id="fe4c0-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="fe4c0-108">**Para especificar um espaço de tabela para uma tabela de log de artigo**:</span><span class="sxs-lookup"><span data-stu-id="fe4c0-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="fe4c0-109">Especifique um espaço de tabela na caixa de diálogo **Propriedades de Artigo** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="fe4c0-110">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fe4c0-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="fe4c0-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fe4c0-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="fe4c0-112">Para usar **sp_changearticle**, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe4c0-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="fe4c0-113">O nome do Publicador Oracle para o parâmetro **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="fe4c0-114">O nome da publicação Oracle para o parâmetro **@publication** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="fe4c0-115">O nome do artigo para o parâmetro **@article** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="fe4c0-116">Um valor de ' tablespace ' para o parâmetro **@property** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="fe4c0-117">O nome do espaço de tabela para o parâmetro **@value** .</span><span class="sxs-lookup"><span data-stu-id="fe4c0-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4c0-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe4c0-118">See Also</span></span>  
 <span data-ttu-id="fe4c0-119">[Configurar um Publicador Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="fe4c0-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="fe4c0-120">Objetos criados no Publicador Oracle</span><span class="sxs-lookup"><span data-stu-id="fe4c0-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
