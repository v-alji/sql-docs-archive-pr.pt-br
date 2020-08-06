---
title: Restaurar do PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684363"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="c85fe-102">Restaurar do PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c85fe-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="c85fe-103">Você pode usar o recurso Restaurar do PowerPivot no SQL Server Management Studio para criar um novo banco de dados modelo de tabela em uma instância do Analysis Services (executando em modo Tabular) ou restaurar para um banco de dados existente de uma pasta de trabalho PowerPivot (.xlsx).</span><span class="sxs-lookup"><span data-stu-id="c85fe-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c85fe-104">O modelo de projeto Importar do PowerPivot no SQL Server Data Tools fornece funcionalidade semelhante.</span><span class="sxs-lookup"><span data-stu-id="c85fe-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="c85fe-105">Para obter mais informações, consulte [Importar do PowerPivot &#40;SSAS tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c85fe-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="c85fe-106">Ao usar Restaurar do PowerPivot, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c85fe-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="c85fe-107">Para usar o recurso Restaurar do PowerPivot, você deverá estar conectado como membro da função Administradores de Servidor na instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c85fe-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="c85fe-108">A conta de serviço da instância do Analysis Services deve ter permissões de leitura no arquivo da pasta de trabalho que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="c85fe-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="c85fe-109">Por padrão, quando você restaura um banco de dados do PowerPivot, a propriedade Informações de Representação da Fonte de Dados do banco de dados modelo de tabela é definida como padrão, que especifica a conta de serviço da instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c85fe-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="c85fe-110">É recomendável alterar as credenciais de representação para uma conta de usuário do Windows em Propriedades do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c85fe-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="c85fe-111">Para obter mais informações, consulte [Representação &#40;SSAS de Tabela&#41;](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c85fe-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="c85fe-112">Os dados no modelo de dados PowerPivot serão copiados para um banco de dados modelo de tabela novo ou existente na instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c85fe-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="c85fe-113">Se sua pasta de trabalho PowerPivot contiver tabelas vinculadas, elas serão recriadas como uma tabela sem uma fonte de dados, semelhante a uma tabela criada usando Colar em nova tabela.</span><span class="sxs-lookup"><span data-stu-id="c85fe-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="c85fe-114">Para restaurar do PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c85fe-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="c85fe-115">No SSMS, na instância do Active Directory para a qual você deseja restaurar, clique com o botão direito em **Bancos de dados**e clique em **Restaurar do PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="c85fe-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="c85fe-116">Na caixa de diálogo **Restaurar do PowerPivot** , em **Restaurar Origem**, em **Arquivo de backup**, clique em **Procurar**e selecione um arquivo .abf ou .xslx do qual restaurar.</span><span class="sxs-lookup"><span data-stu-id="c85fe-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="c85fe-117">Em **Destino da Restauração**, em **Restaurar banco de dados**, digite um nome de um banco de dados novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="c85fe-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="c85fe-118">Se você não especificar um nome, o nome da pasta de trabalho será usado.</span><span class="sxs-lookup"><span data-stu-id="c85fe-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="c85fe-119">Em **Local de armazenamento**, clique em **Procurar**e selecione um local para armazenar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c85fe-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="c85fe-120">Em **Opções**, deixe **Incluir informações de segurança** marcado.</span><span class="sxs-lookup"><span data-stu-id="c85fe-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="c85fe-121">Ao restaurar de uma pasta de trabalho PowerPivot, essa configuração não se aplica.</span><span class="sxs-lookup"><span data-stu-id="c85fe-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85fe-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c85fe-122">See Also</span></span>  
 <span data-ttu-id="c85fe-123">[Bancos de dados de modelo de tabela &#40;SSAS de tabela&#41;](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c85fe-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c85fe-124">Importar do PowerPivot &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="c85fe-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
