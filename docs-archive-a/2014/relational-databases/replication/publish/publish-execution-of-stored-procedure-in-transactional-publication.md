---
title: Publicar a execução de um procedimento armazenado em uma publicação transacional (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570605"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="010b6-102">Publicar a execução de um procedimento armazenado em uma publicação transacional (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="010b6-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="010b6-103">Especifique que a execução de um procedimento armazenado (em vez de executar somente sua definição) deve ser publicada na caixa de diálogo **Propriedades de Artigo – \<Article>** .</span><span class="sxs-lookup"><span data-stu-id="010b6-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="010b6-104">Essa caixa de diálogo fica disponível no Assistente para Nova Publicação e na caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="010b6-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="010b6-105">Para obter mais informações sobre como usar o assistente e acessar a caixa de diálogo, consulte [Criar uma publicação](create-a-publication.md) e [Exibir e modificar as propriedades da publicação](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="010b6-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="010b6-106">A definição do procedimento (instrução CREATE PROCEDURE) será replicada para o Assinante quando a inscrição for inicializada. Quando o procedimento armazenado for executado no Publicador, a replicação executará o procedimento correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="010b6-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="010b6-107">Para publicar a execução de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="010b6-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="010b6-108">Na página **Artigos** do Assistente para Nova Publicação ou na caixa de diálogo **Propriedades da Publicação – \<Publication>** , selecione um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="010b6-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="010b6-109">Clique em **Propriedade de Artigo**, depois em **Definir Propriedades de Procedimento Armazenado Realçado**.</span><span class="sxs-lookup"><span data-stu-id="010b6-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="010b6-110">Na caixa de diálogo **Propriedades de Artigo – \<Article>** , especifique um dos seguintes valores para a opção **Replicar**:</span><span class="sxs-lookup"><span data-stu-id="010b6-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="010b6-111">**Execução do procedimento armazenado**</span><span class="sxs-lookup"><span data-stu-id="010b6-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="010b6-112">**Execução em uma transação serializável do SP**</span><span class="sxs-lookup"><span data-stu-id="010b6-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="010b6-113">Essa é a opção recomendada, uma vez que ela replica a execução do procedimento apenas se o procedimento for executado dentro do contexto de uma transação serializável.</span><span class="sxs-lookup"><span data-stu-id="010b6-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="010b6-114">Se o procedimento armazenado for executado fora de uma transação serializável, as alterações dos dados nas tabelas publicadas serão replicadas como uma série de instruções DML (Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="010b6-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="010b6-115">Se você estiver na caixa de diálogo **Propriedades da Publicação – \<Publication>** , clique em **OK** para salvar e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="010b6-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="010b6-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="010b6-116">See Also</span></span>  
 [<span data-ttu-id="010b6-117">Publicando a execução de procedimento armazenado em replicação transacional</span><span class="sxs-lookup"><span data-stu-id="010b6-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
