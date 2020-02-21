## <a name="cds-contacts-v2-to-contacts"></a><span data-ttu-id="e5eb6-101">CDS 連絡先 V2 を連絡先へ</span><span class="sxs-lookup"><span data-stu-id="e5eb6-101">CDS Contacts V2 to contacts</span></span>

<span data-ttu-id="e5eb6-102">このテンプレートは、Finance and Operations アプリと Common Data Service 間でデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="e5eb6-102">This template synchronizes data between Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="e5eb6-103">ソース フィルター: (AssociatedContactType = 1)</span><span class="sxs-lookup"><span data-stu-id="e5eb6-103">Source filter: (AssociatedContactType = 1)</span></span>

<span data-ttu-id="e5eb6-104">取消済ソース フィルター: msdyn_contactforvendor eq true および msdyn_sellable eq false および msdyn_contactpersonid ne ''</span><span class="sxs-lookup"><span data-stu-id="e5eb6-104">Reversed source filter: msdyn_contactforvendor eq true and msdyn_sellable eq false and msdyn_contactpersonid ne ''</span></span>

<span data-ttu-id="e5eb6-105">Finance and Operations フィールド</span><span class="sxs-lookup"><span data-stu-id="e5eb6-105">Finance and Operations field</span></span> | <span data-ttu-id="e5eb6-106">タイプのマッピング</span><span class="sxs-lookup"><span data-stu-id="e5eb6-106">Map type</span></span> | <span data-ttu-id="e5eb6-107">その他の Dynamics 365 フィールド</span><span class="sxs-lookup"><span data-stu-id="e5eb6-107">Other Dynamics 365 field</span></span> | <span data-ttu-id="e5eb6-108">既定値</span><span class="sxs-lookup"><span data-stu-id="e5eb6-108">Default value</span></span>
---|---|---|---
<span data-ttu-id="e5eb6-109">CONTACTPERSONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-109">CONTACTPERSONPARTYNUMBER</span></span> | = | <span data-ttu-id="e5eb6-110">msdyn_partynumber</span><span class="sxs-lookup"><span data-stu-id="e5eb6-110">msdyn_partynumber</span></span> | 
<span data-ttu-id="e5eb6-111">ASSOCIATEDCONTACTTYPE</span><span class="sxs-lookup"><span data-stu-id="e5eb6-111">ASSOCIATEDCONTACTTYPE</span></span> | << | <span data-ttu-id="e5eb6-112">なし</span><span class="sxs-lookup"><span data-stu-id="e5eb6-112">none</span></span> | <span data-ttu-id="e5eb6-113">仕入先</span><span class="sxs-lookup"><span data-stu-id="e5eb6-113">Vendor</span></span>
<span data-ttu-id="e5eb6-114">FIRSTNAME</span><span class="sxs-lookup"><span data-stu-id="e5eb6-114">FIRSTNAME</span></span> | = | <span data-ttu-id="e5eb6-115">firstname</span><span class="sxs-lookup"><span data-stu-id="e5eb6-115">firstname</span></span> | 
<span data-ttu-id="e5eb6-116">MIDDLENAME</span><span class="sxs-lookup"><span data-stu-id="e5eb6-116">MIDDLENAME</span></span> | = | <span data-ttu-id="e5eb6-117">middlename</span><span class="sxs-lookup"><span data-stu-id="e5eb6-117">middlename</span></span> | 
<span data-ttu-id="e5eb6-118">LASTNAME</span><span class="sxs-lookup"><span data-stu-id="e5eb6-118">LASTNAME</span></span> | = | <span data-ttu-id="e5eb6-119">lastname</span><span class="sxs-lookup"><span data-stu-id="e5eb6-119">lastname</span></span> | 
<span data-ttu-id="e5eb6-120">ASSOCIATEDCONTACTNUMBER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-120">ASSOCIATEDCONTACTNUMBER</span></span> | = | <span data-ttu-id="e5eb6-121">msdyn_vendorcontactid.msdyn_vendoraccountnumber</span><span class="sxs-lookup"><span data-stu-id="e5eb6-121">msdyn_vendorcontactid.msdyn_vendoraccountnumber</span></span> | 
<span data-ttu-id="e5eb6-122">PRIMARYADDRESSCITY</span><span class="sxs-lookup"><span data-stu-id="e5eb6-122">PRIMARYADDRESSCITY</span></span> | = | <span data-ttu-id="e5eb6-123">address1_city</span><span class="sxs-lookup"><span data-stu-id="e5eb6-123">address1_city</span></span> | 
<span data-ttu-id="e5eb6-124">PRIMARYADDRESSCOUNTRYREGIONID</span><span class="sxs-lookup"><span data-stu-id="e5eb6-124">PRIMARYADDRESSCOUNTRYREGIONID</span></span> | = | <span data-ttu-id="e5eb6-125">address1_country</span><span class="sxs-lookup"><span data-stu-id="e5eb6-125">address1_country</span></span> | 
<span data-ttu-id="e5eb6-126">PRIMARYADDRESSCOUNTYID</span><span class="sxs-lookup"><span data-stu-id="e5eb6-126">PRIMARYADDRESSCOUNTYID</span></span> | = | <span data-ttu-id="e5eb6-127">address1_county</span><span class="sxs-lookup"><span data-stu-id="e5eb6-127">address1_county</span></span> | 
<span data-ttu-id="e5eb6-128">PRIMARYFAXNUMBER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-128">PRIMARYFAXNUMBER</span></span> | = | <span data-ttu-id="e5eb6-129">FAX</span><span class="sxs-lookup"><span data-stu-id="e5eb6-129">fax</span></span> | 
<span data-ttu-id="e5eb6-130">PRIMARYADDRESSSTATEID</span><span class="sxs-lookup"><span data-stu-id="e5eb6-130">PRIMARYADDRESSSTATEID</span></span> | = | <span data-ttu-id="e5eb6-131">address1_stateorprovince</span><span class="sxs-lookup"><span data-stu-id="e5eb6-131">address1_stateorprovince</span></span> | 
<span data-ttu-id="e5eb6-132">PRIMARYADDRESSSTREET</span><span class="sxs-lookup"><span data-stu-id="e5eb6-132">PRIMARYADDRESSSTREET</span></span> | = | <span data-ttu-id="e5eb6-133">address1_line1</span><span class="sxs-lookup"><span data-stu-id="e5eb6-133">address1_line1</span></span> | 
<span data-ttu-id="e5eb6-134">PRIMARYADDRESSZIPCODE</span><span class="sxs-lookup"><span data-stu-id="e5eb6-134">PRIMARYADDRESSZIPCODE</span></span> | = | <span data-ttu-id="e5eb6-135">address1_postalcode</span><span class="sxs-lookup"><span data-stu-id="e5eb6-135">address1_postalcode</span></span> | 
<span data-ttu-id="e5eb6-136">PRIMARYPHONENUMBER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-136">PRIMARYPHONENUMBER</span></span> | = | <span data-ttu-id="e5eb6-137">telephone1</span><span class="sxs-lookup"><span data-stu-id="e5eb6-137">telephone1</span></span> | 
<span data-ttu-id="e5eb6-138">PRIMARYEMAILADDRESS</span><span class="sxs-lookup"><span data-stu-id="e5eb6-138">PRIMARYEMAILADDRESS</span></span> | = | <span data-ttu-id="e5eb6-139">emailaddress1</span><span class="sxs-lookup"><span data-stu-id="e5eb6-139">emailaddress1</span></span> | 
<span data-ttu-id="e5eb6-140">EMPLOYMENTDEPARTMENT</span><span class="sxs-lookup"><span data-stu-id="e5eb6-140">EMPLOYMENTDEPARTMENT</span></span> | = | <span data-ttu-id="e5eb6-141">department</span><span class="sxs-lookup"><span data-stu-id="e5eb6-141">department</span></span> | 
<span data-ttu-id="e5eb6-142">NOTES</span><span class="sxs-lookup"><span data-stu-id="e5eb6-142">NOTES</span></span> | = | <span data-ttu-id="e5eb6-143">description</span><span class="sxs-lookup"><span data-stu-id="e5eb6-143">description</span></span> | 
<span data-ttu-id="e5eb6-144">GENDER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-144">GENDER</span></span> | >< | <span data-ttu-id="e5eb6-145">gendercode</span><span class="sxs-lookup"><span data-stu-id="e5eb6-145">gendercode</span></span> | 
<span data-ttu-id="e5eb6-146">GOVERNMENTIDENTIFICATIONNUMBER</span><span class="sxs-lookup"><span data-stu-id="e5eb6-146">GOVERNMENTIDENTIFICATIONNUMBER</span></span> | = | <span data-ttu-id="e5eb6-147">governmentid</span><span class="sxs-lookup"><span data-stu-id="e5eb6-147">governmentid</span></span> | 
<span data-ttu-id="e5eb6-148">PRIMARYURL</span><span class="sxs-lookup"><span data-stu-id="e5eb6-148">PRIMARYURL</span></span> | = | <span data-ttu-id="e5eb6-149">websiteurl</span><span class="sxs-lookup"><span data-stu-id="e5eb6-149">websiteurl</span></span> | 
<span data-ttu-id="e5eb6-150">MARITALSTATUS</span><span class="sxs-lookup"><span data-stu-id="e5eb6-150">MARITALSTATUS</span></span> | >< | <span data-ttu-id="e5eb6-151">familystatuscode</span><span class="sxs-lookup"><span data-stu-id="e5eb6-151">familystatuscode</span></span> | 
<span data-ttu-id="e5eb6-152">ISRECEIVINGDIRECTMAIL</span><span class="sxs-lookup"><span data-stu-id="e5eb6-152">ISRECEIVINGDIRECTMAIL</span></span> | >< | <span data-ttu-id="e5eb6-153">donotemail</span><span class="sxs-lookup"><span data-stu-id="e5eb6-153">donotemail</span></span> | 
<span data-ttu-id="e5eb6-154">EMPLOYMENTPROFESSION</span><span class="sxs-lookup"><span data-stu-id="e5eb6-154">EMPLOYMENTPROFESSION</span></span> | = | <span data-ttu-id="e5eb6-155">jobtitle</span><span class="sxs-lookup"><span data-stu-id="e5eb6-155">jobtitle</span></span> | 
<span data-ttu-id="e5eb6-156">SPOUSENAME</span><span class="sxs-lookup"><span data-stu-id="e5eb6-156">SPOUSENAME</span></span> | = | <span data-ttu-id="e5eb6-157">spousesname</span><span class="sxs-lookup"><span data-stu-id="e5eb6-157">spousesname</span></span> | 
<span data-ttu-id="e5eb6-158">なし</span><span class="sxs-lookup"><span data-stu-id="e5eb6-158">none</span></span> | >> | <span data-ttu-id="e5eb6-159">msdyn_contactforvendor</span><span class="sxs-lookup"><span data-stu-id="e5eb6-159">msdyn_contactforvendor</span></span> | <span data-ttu-id="e5eb6-160">True</span><span class="sxs-lookup"><span data-stu-id="e5eb6-160">True</span></span>
<span data-ttu-id="e5eb6-161">CONTACTPERSONID</span><span class="sxs-lookup"><span data-stu-id="e5eb6-161">CONTACTPERSONID</span></span> | = | <span data-ttu-id="e5eb6-162">msdyn_contactpersonid</span><span class="sxs-lookup"><span data-stu-id="e5eb6-162">msdyn_contactpersonid</span></span> | 