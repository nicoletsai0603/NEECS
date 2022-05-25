
//自訂義alert，來源sweetalert
function CustAlert(IsOK, title, html, url, IsDialogMode) {
    Swal.fire({
        icon: IsOK.toString().toUpperCase() == 'TRUE' ? 'success' : 'error',
        title: title,
        html: html,
        confirmButtonText: '確定',
        allowOutsideClick: false
    }).then(function (result) {
        if (result.value) {
            if (url) {
                //若為彈跳視窗模式，則關閉彈跳視窗，並且導頁至指定頁面
                if (IsDialogMode.toString().toUpperCase() == 'TRUE') {
                    parent.$("#myModal").modal('hide');
                    parent.location.href = url.replace('&amp;', '&');
                }
                else {
                    location.href = url.replace('&amp;', '&');
                }
            }
        }
        //parent.$("#myModal").modal('hide');
    });
}

//彈跳視窗自適應框高
function RePopBoxHeight(height) {
    $('.modal-body').css("height", (height + 100) + 'px');
    $('.modal-body > iframe').css("height", (height + 80) + 'px');
}

//控制項是否可編輯
function ControlModify(IsOk) {
    if (IsOk == "False") {
        $("#CaseEdit input").attr("disabled", "disabled");
        $("#CaseEdit select").attr("disabled", "disabled");
        $("#CaseEdit textarea").attr("disabled", "disabled");
        $("#CaseEdit input[type=submit]").attr("class", "display_none");
        $("#CaseEdit input[type=button]").attr("class", "display_none");
        $("#CaseEdit .InputControl").attr("class", "display_none");
        $("#CaseEdit #add").attr("class", "display_none");
        //例外處理
        $("#CaseEdit input[name=ProfilePay]").removeAttr("disabled");
        $("#CaseEdit input[type=hidden]").removeAttr("disabled");
    }
}

$(document).ready(function () {
    $('.dropdown-menu a.dropdown-toggle').on('click', function (e) {
        var $el = $(this);
        $el.toggleClass('active-dropdown');
        var $parent = $(this).offsetParent(".dropdown-menu");
        if (!$(this).next().hasClass('show')) {
            $(this).parents('.dropdown-menu').first().find('.show').removeClass("show");
        }
        var $subMenu = $(this).next(".dropdown-menu");
        $subMenu.toggleClass('show');

        $(this).parent("li").toggleClass('show');

        $(this).parents('li.nav-item.dropdown.show').on('hidden.bs.dropdown', function (e) {
            $('.dropdown-menu .show').removeClass("show");
            $el.removeClass('active-dropdown');
        });

        if (!$parent.parent().hasClass('navbar-nav')) {
            $el.next().css({ "top": $el[0].offsetTop, "left": $parent.outerWidth() - 4 });
        }

        return false;
    });

    //身分證前端驗證註冊
    //jQuery.validator.addMethod("IDCardNumber",
    //    function (value, element, param) {
    //        var Ischeck = false;
    //        $.ajax({
    //            type: "GET",
    //            url: "/Valid/CheckIdno",
    //            data: { 'Idno': value },
    //            async: false,
    //            beforeSend: function (xhr) {
    //                xhr.setRequestHeader("requestverificationtoken",
    //                    $('input:hidden[name="__RequestVerificationToken"]').val());
    //            },
    //            success: function (e) {
    //                Ischeck = Boolean(e);
    //            }
    //        });
    //    return Ischeck;
    //    });
    //jQuery.validator.unobtrusive.adapters.addBool("IDCardNumber");
});

var AutoAddrData = [
    { city: "臺北市中正區", zip: "100" },
    { city: "臺北市大同區", zip: "103" },
    { city: "臺北市中山區", zip: "104" },
    { city: "臺北市松山區", zip: "105" },
    { city: "臺北市大安區", zip: "106" },
    { city: "臺北市萬華區", zip: "108" },
    { city: "臺北市信義區", zip: "110" },
    { city: "臺北市士林區", zip: "111" },
    { city: "臺北市北投區", zip: "112" },
    { city: "臺北市內湖區", zip: "114" },
    { city: "臺北市南港區", zip: "115" },
    { city: "臺北市文山區", zip: "116" },
    { city: "基隆市仁愛區", zip: "200" },
    { city: "基隆市信義區", zip: "201" },
    { city: "基隆市中正區", zip: "202" },
    { city: "基隆市中山區", zip: "203" },
    { city: "基隆市安樂區", zip: "204" },
    { city: "基隆市暖暖區", zip: "205" },
    { city: "基隆市七堵區", zip: "206" },
    { city: "新北市萬里區", zip: "207" },
    { city: "新北市金山區", zip: "208" },
    { city: "連江縣南竿鄉", zip: "209" },
    { city: "連江縣北竿鄉", zip: "210" },
    { city: "連江縣莒光鄉", zip: "211" },
    { city: "連江縣東引鄉", zip: "212" },
    { city: "新北市板橋區", zip: "220" },
    { city: "新北市汐止區", zip: "221" },
    { city: "新北市深坑區", zip: "222" },
    { city: "新北市石碇區", zip: "223" },
    { city: "新北市瑞芳區", zip: "224" },
    { city: "新北市平溪區", zip: "226" },
    { city: "新北市雙溪區", zip: "227" },
    { city: "新北市貢寮區", zip: "228" },
    { city: "新北市新店區", zip: "231" },
    { city: "新北市坪林區", zip: "232" },
    { city: "新北市烏來區", zip: "233" },
    { city: "新北市永和區", zip: "234" },
    { city: "新北市中和區", zip: "235" },
    { city: "新北市土城區", zip: "236" },
    { city: "新北市三峽區", zip: "237" },
    { city: "新北市樹林區", zip: "238" },
    { city: "新北市鶯歌區", zip: "239" },
    { city: "新北市三重區", zip: "241" },
    { city: "新北市新莊區", zip: "242" },
    { city: "新北市泰山區", zip: "243" },
    { city: "新北市林口區", zip: "244" },
    { city: "新北市蘆洲區", zip: "247" },
    { city: "新北市五股區", zip: "248" },
    { city: "新北市八里區", zip: "249" },
    { city: "新北市淡水區", zip: "251" },
    { city: "新北市三芝區", zip: "252" },
    { city: "新北市石門區", zip: "253" },
    { city: "宜蘭縣宜蘭市", zip: "260" },
    { city: "宜蘭縣頭城鎮", zip: "261" },
    { city: "宜蘭縣礁溪鄉", zip: "262" },
    { city: "宜蘭縣壯圍鄉", zip: "263" },
    { city: "宜蘭縣員山鄉", zip: "264" },
    { city: "宜蘭縣羅東鎮", zip: "265" },
    { city: "宜蘭縣三星鄉", zip: "266" },
    { city: "宜蘭縣大同鄉", zip: "267" },
    { city: "宜蘭縣五結鄉", zip: "268" },
    { city: "宜蘭縣冬山鄉", zip: "269" },
    { city: "宜蘭縣蘇澳鎮", zip: "270" },
    { city: "宜蘭縣南澳鄉", zip: "272" },
    { city: "新竹市", zip: "300" },
    { city: "新竹縣竹北市", zip: "302" },
    { city: "新竹縣湖口鄉", zip: "303" },
    { city: "新竹縣新豐鄉", zip: "304" },
    { city: "新竹縣新埔鎮", zip: "305" },
    { city: "新竹縣關西鎮", zip: "306" },
    { city: "新竹縣芎林鄉", zip: "307" },
    { city: "新竹縣寶山鄉", zip: "308" },
    { city: "新竹縣竹東鎮", zip: "310" },
    { city: "新竹縣五峰鄉", zip: "311" },
    { city: "新竹縣橫山鄉", zip: "312" },
    { city: "新竹縣尖石鄉", zip: "313" },
    { city: "新竹縣北埔鄉", zip: "314" },
    { city: "新竹縣峨眉鄉", zip: "315" },
    { city: "桃園市中壢區", zip: "320" },
    { city: "桃園市平鎮區", zip: "324" },
    { city: "桃園市龍潭區", zip: "325" },
    { city: "桃園市楊梅區", zip: "326" },
    { city: "桃園市新屋區", zip: "327" },
    { city: "桃園市觀音區", zip: "328" },
    { city: "桃園市桃園區", zip: "330" },
    { city: "桃園市龜山區", zip: "333" },
    { city: "桃園市八德區", zip: "334" },
    { city: "桃園市大溪區", zip: "335" },
    { city: "桃園市復興區", zip: "336" },
    { city: "桃園市大園區", zip: "337" },
    { city: "桃園市蘆竹區", zip: "338" },
    { city: "苗栗縣竹南鎮", zip: "350" },
    { city: "苗栗縣頭份鎮", zip: "351" },
    { city: "苗栗縣三灣鄉", zip: "352" },
    { city: "苗栗縣南庄鄉", zip: "353" },
    { city: "苗栗縣獅潭鄉", zip: "354" },
    { city: "苗栗縣後龍鎮", zip: "356" },
    { city: "苗栗縣通霄鎮", zip: "357" },
    { city: "苗栗縣苑裡鎮", zip: "358" },
    { city: "苗栗縣苗栗市", zip: "360" },
    { city: "苗栗縣造橋鄉", zip: "361" },
    { city: "苗栗縣頭屋鄉", zip: "362" },
    { city: "苗栗縣公館鄉", zip: "363" },
    { city: "苗栗縣大湖鄉", zip: "364" },
    { city: "苗栗縣泰安鄉", zip: "365" },
    { city: "苗栗縣銅鑼鄉", zip: "366" },
    { city: "苗栗縣三義鄉", zip: "367" },
    { city: "苗栗縣西湖鄉", zip: "368" },
    { city: "苗栗縣卓蘭鎮", zip: "369" },
    { city: "臺中市中區", zip: "400" },
    { city: "臺中市東區", zip: "401" },
    { city: "臺中市南區", zip: "402" },
    { city: "臺中市西區", zip: "403" },
    { city: "臺中市北區", zip: "404" },
    { city: "臺中市北屯區", zip: "406" },
    { city: "臺中市西屯區", zip: "407" },
    { city: "臺中市南屯區", zip: "408" },
    { city: "臺中市太平區", zip: "411" },
    { city: "臺中市大里區", zip: "412" },
    { city: "臺中市霧峰區", zip: "413" },
    { city: "臺中市烏日區", zip: "414" },
    { city: "臺中市豐原區", zip: "420" },
    { city: "臺中市后里區", zip: "421" },
    { city: "臺中市石岡區", zip: "422" },
    { city: "臺中市東勢區", zip: "423" },
    { city: "臺中市和平區", zip: "424" },
    { city: "臺中市新社區", zip: "426" },
    { city: "臺中市潭子區", zip: "427" },
    { city: "臺中市大雅區", zip: "428" },
    { city: "臺中市神岡區", zip: "429" },
    { city: "臺中市大肚區", zip: "432" },
    { city: "臺中市沙鹿區", zip: "433" },
    { city: "臺中市龍井區", zip: "434" },
    { city: "臺中市梧棲區", zip: "435" },
    { city: "臺中市清水區", zip: "436" },
    { city: "臺中市大甲區", zip: "437" },
    { city: "臺中市外埔區", zip: "438" },
    { city: "臺中市大安區", zip: "439" },
    { city: "彰化縣彰化市", zip: "500" },
    { city: "彰化縣芬園鄉", zip: "502" },
    { city: "彰化縣花壇鄉", zip: "503" },
    { city: "彰化縣秀水鄉", zip: "504" },
    { city: "彰化縣鹿港鎮", zip: "505" },
    { city: "彰化縣福興鄉", zip: "506" },
    { city: "彰化縣線西鄉", zip: "507" },
    { city: "彰化縣和美鎮", zip: "508" },
    { city: "彰化縣伸港鄉", zip: "509" },
    { city: "彰化縣員林鎮", zip: "510" },
    { city: "彰化縣社頭鄉", zip: "511" },
    { city: "彰化縣永靖鄉", zip: "512" },
    { city: "彰化縣埔心鄉", zip: "513" },
    { city: "彰化縣溪湖鎮", zip: "514" },
    { city: "彰化縣大村鄉", zip: "515" },
    { city: "彰化縣埔鹽鄉", zip: "516" },
    { city: "彰化縣田中鎮", zip: "520" },
    { city: "彰化縣北斗鎮", zip: "521" },
    { city: "彰化縣田尾鄉", zip: "522" },
    { city: "彰化縣埤頭鄉", zip: "523" },
    { city: "彰化縣溪州鄉", zip: "524" },
    { city: "彰化縣竹塘鄉", zip: "525" },
    { city: "彰化縣二林鎮", zip: "526" },
    { city: "彰化縣大城鄉", zip: "527" },
    { city: "彰化縣芳苑鄉", zip: "528" },
    { city: "彰化縣二水鄉", zip: "530" },
    { city: "南投縣南投市", zip: "540" },
    { city: "南投縣中寮鄉", zip: "541" },
    { city: "南投縣草屯鎮", zip: "542" },
    { city: "南投縣國姓鄉", zip: "544" },
    { city: "南投縣埔里鎮", zip: "545" },
    { city: "南投縣仁愛鄉", zip: "546" },
    { city: "南投縣名間鄉", zip: "551" },
    { city: "南投縣集集鎮", zip: "552" },
    { city: "南投縣水里鄉", zip: "553" },
    { city: "南投縣魚池鄉", zip: "555" },
    { city: "南投縣信義鄉", zip: "556" },
    { city: "南投縣竹山鎮", zip: "557" },
    { city: "南投縣鹿谷鄉", zip: "558" },
    { city: "嘉義市", zip: "600" },
    { city: "嘉義縣番路鄉", zip: "602" },
    { city: "嘉義縣梅山鄉", zip: "603" },
    { city: "嘉義縣竹崎鄉", zip: "604" },
    { city: "嘉義縣阿里山鄉", zip: "605" },
    { city: "嘉義縣中埔鄉", zip: "606" },
    { city: "嘉義縣大埔鄉", zip: "607" },
    { city: "嘉義縣水上鄉", zip: "608" },
    { city: "嘉義縣鹿草鄉", zip: "611" },
    { city: "嘉義縣太保市", zip: "612" },
    { city: "嘉義縣朴子市", zip: "613" },
    { city: "嘉義縣東石鄉", zip: "614" },
    { city: "嘉義縣六腳鄉", zip: "615" },
    { city: "嘉義縣新港鄉", zip: "616" },
    { city: "嘉義縣民雄鄉", zip: "621" },
    { city: "嘉義縣大林鎮", zip: "622" },
    { city: "嘉義縣溪口鄉", zip: "623" },
    { city: "嘉義縣義竹鄉", zip: "624" },
    { city: "嘉義縣布袋鎮", zip: "625" },
    { city: "雲林縣斗南鎮", zip: "630" },
    { city: "雲林縣大埤鄉", zip: "631" },
    { city: "雲林縣虎尾鎮", zip: "632" },
    { city: "雲林縣土庫鎮", zip: "633" },
    { city: "雲林縣褒忠鄉", zip: "634" },
    { city: "雲林縣東勢鄉", zip: "635" },
    { city: "雲林縣臺西鄉", zip: "636" },
    { city: "雲林縣崙背鄉", zip: "637" },
    { city: "雲林縣麥寮鄉", zip: "638" },
    { city: "雲林縣斗六市", zip: "640" },
    { city: "雲林縣林內鄉", zip: "643" },
    { city: "雲林縣古坑鄉", zip: "646" },
    { city: "雲林縣莿桐鄉", zip: "647" },
    { city: "雲林縣西螺鎮", zip: "648" },
    { city: "雲林縣二崙鄉", zip: "649" },
    { city: "雲林縣北港鎮", zip: "651" },
    { city: "雲林縣水林鄉", zip: "652" },
    { city: "雲林縣口湖鄉", zip: "653" },
    { city: "雲林縣四湖鄉", zip: "654" },
    { city: "雲林縣元長鄉", zip: "655" },
    { city: "臺南市中西區", zip: "700" },
    { city: "臺南市東區", zip: "701" },
    { city: "臺南市南區", zip: "702" },
    { city: "臺南市西區", zip: "703" },
    { city: "臺南市北區", zip: "704" },
    { city: "臺南市安平區", zip: "708" },
    { city: "臺南市安南區", zip: "709" },
    { city: "臺南市永康區", zip: "710" },
    { city: "臺南市歸仁區", zip: "711" },
    { city: "臺南市新化區", zip: "712" },
    { city: "臺南市左鎮區", zip: "713" },
    { city: "臺南市玉井區", zip: "714" },
    { city: "臺南市楠西區", zip: "715" },
    { city: "臺南市南化區", zip: "716" },
    { city: "臺南市仁德區", zip: "717" },
    { city: "臺南市關廟區", zip: "718" },
    { city: "臺南市龍崎區", zip: "719" },
    { city: "臺南市官田區", zip: "720" },
    { city: "臺南市麻豆區", zip: "721" },
    { city: "臺南市佳里區", zip: "722" },
    { city: "臺南市西港區", zip: "723" },
    { city: "臺南市七股區", zip: "724" },
    { city: "臺南市將軍區", zip: "725" },
    { city: "臺南市學甲區", zip: "726" },
    { city: "臺南市北門區", zip: "727" },
    { city: "臺南市新營區", zip: "730" },
    { city: "臺南市後壁區", zip: "731" },
    { city: "臺南市白河區", zip: "732" },
    { city: "臺南市東山區", zip: "733" },
    { city: "臺南市六甲區", zip: "734" },
    { city: "臺南市下營區", zip: "735" },
    { city: "臺南市柳營區", zip: "736" },
    { city: "臺南市鹽水區", zip: "737" },
    { city: "臺南市善化區", zip: "741" },
    { city: "臺南市大內區", zip: "742" },
    { city: "臺南市山上區", zip: "743" },
    { city: "臺南市新市區", zip: "744" },
    { city: "臺南市安定區", zip: "745" },
    { city: "高雄市新興區", zip: "800" },
    { city: "高雄市前金區", zip: "801" },
    { city: "高雄市苓雅區", zip: "802" },
    { city: "高雄市鹽埕區", zip: "803" },
    { city: "高雄市鼓山區", zip: "804" },
    { city: "高雄市旗津區", zip: "805" },
    { city: "高雄市前鎮區", zip: "806" },
    { city: "高雄市三民區", zip: "807" },
    { city: "高雄市楠梓區", zip: "811" },
    { city: "高雄市小港區", zip: "812" },
    { city: "高雄市左營區", zip: "813" },
    { city: "高雄市仁武區", zip: "814" },
    { city: "高雄市大社區", zip: "815" },
    { city: "高雄市岡山區", zip: "820" },
    { city: "高雄市路竹區", zip: "821" },
    { city: "高雄市阿蓮區", zip: "822" },
    { city: "高雄市田寮區", zip: "823" },
    { city: "高雄市燕巢區", zip: "824" },
    { city: "高雄市橋頭區", zip: "825" },
    { city: "高雄市梓官區", zip: "826" },
    { city: "高雄市彌陀區", zip: "827" },
    { city: "高雄市永安區", zip: "828" },
    { city: "高雄市湖內區", zip: "829" },
    { city: "高雄市鳳山區", zip: "830" },
    { city: "高雄市大寮區", zip: "831" },
    { city: "高雄市林園區", zip: "832" },
    { city: "高雄市鳥松區", zip: "833" },
    { city: "高雄市大樹區", zip: "840" },
    { city: "高雄市旗山區", zip: "842" },
    { city: "高雄市美濃區", zip: "843" },
    { city: "高雄市六龜區", zip: "844" },
    { city: "高雄市內門區", zip: "845" },
    { city: "高雄市杉林區", zip: "846" },
    { city: "高雄市甲仙區", zip: "847" },
    { city: "高雄市桃源區", zip: "848" },
    { city: "高雄市那瑪夏區", zip: "849" },
    { city: "高雄市茂林區", zip: "851" },
    { city: "高雄市茄萣區", zip: "852" },
    { city: "澎湖縣馬公市", zip: "880" },
    { city: "澎湖縣西嶼鄉", zip: "881" },
    { city: "澎湖縣望安鄉", zip: "882" },
    { city: "澎湖縣七美鄉", zip: "883" },
    { city: "澎湖縣白沙鄉", zip: "884" },
    { city: "澎湖縣湖西鄉", zip: "885" },
    { city: "金門縣金沙鎮", zip: "890" },
    { city: "金門縣金湖鎮", zip: "891" },
    { city: "金門縣金寧鄉", zip: "892" },
    { city: "金門縣金城鎮", zip: "893" },
    { city: "金門縣烈嶼鄉", zip: "894" },
    { city: "金門縣烏坵鄉", zip: "896" },
    { city: "屏東縣屏東市", zip: "900" },
    { city: "屏東縣三地門鄉", zip: "901" },
    { city: "屏東縣霧臺鄉", zip: "902" },
    { city: "屏東縣瑪家鄉", zip: "903" },
    { city: "屏東縣九如鄉", zip: "904" },
    { city: "屏東縣里港鄉", zip: "905" },
    { city: "屏東縣高樹鄉", zip: "906" },
    { city: "屏東縣鹽埔鄉", zip: "907" },
    { city: "屏東縣長治鄉", zip: "908" },
    { city: "屏東縣麟洛鄉", zip: "909" },
    { city: "屏東縣竹田鄉", zip: "911" },
    { city: "屏東縣內埔鄉", zip: "912" },
    { city: "屏東縣萬丹鄉", zip: "913" },
    { city: "屏東縣潮州鎮", zip: "920" },
    { city: "屏東縣泰武鄉", zip: "921" },
    { city: "屏東縣來義鄉", zip: "922" },
    { city: "屏東縣萬巒鄉", zip: "923" },
    { city: "屏東縣崁頂鄉", zip: "924" },
    { city: "屏東縣新埤鄉", zip: "925" },
    { city: "屏東縣南州鄉", zip: "926" },
    { city: "屏東縣林邊鄉", zip: "927" },
    { city: "屏東縣東港鎮", zip: "928" },
    { city: "屏東縣琉球鄉", zip: "929" },
    { city: "屏東縣佳冬鄉", zip: "931" },
    { city: "屏東縣新園鄉", zip: "932" },
    { city: "屏東縣枋寮鄉", zip: "940" },
    { city: "屏東縣枋山鄉", zip: "941" },
    { city: "屏東縣春日鄉", zip: "942" },
    { city: "屏東縣獅子鄉", zip: "943" },
    { city: "屏東縣車城鄉", zip: "944" },
    { city: "屏東縣牡丹鄉", zip: "945" },
    { city: "屏東縣恆春鎮", zip: "946" },
    { city: "屏東縣滿州鄉", zip: "947" },
    { city: "臺東縣臺東市", zip: "950" },
    { city: "臺東縣綠島鄉", zip: "951" },
    { city: "臺東縣蘭嶼鄉", zip: "952" },
    { city: "臺東縣延平鄉", zip: "953" },
    { city: "臺東縣卑南鄉", zip: "954" },
    { city: "臺東縣鹿野鄉", zip: "955" },
    { city: "臺東縣關山鎮", zip: "956" },
    { city: "臺東縣海端鄉", zip: "957" },
    { city: "臺東縣池上鄉", zip: "958" },
    { city: "臺東縣東河鄉", zip: "959" },
    { city: "臺東縣成功鎮", zip: "961" },
    { city: "臺東縣長濱鄉", zip: "962" },
    { city: "臺東縣太麻里鄉", zip: "963" },
    { city: "臺東縣金峰鄉", zip: "964" },
    { city: "臺東縣大武鄉", zip: "965" },
    { city: "臺東縣達仁鄉", zip: "966" },
    { city: "花蓮縣花蓮市", zip: "970" },
    { city: "花蓮縣新城鄉", zip: "971" },
    { city: "花蓮縣秀林鄉", zip: "972" },
    { city: "花蓮縣吉安鄉", zip: "973" },
    { city: "花蓮縣壽豐鄉", zip: "974" },
    { city: "花蓮縣鳳林鎮", zip: "975" },
    { city: "花蓮縣光復鄉", zip: "976" },
    { city: "花蓮縣豐濱鄉", zip: "977" },
    { city: "花蓮縣瑞穗鄉", zip: "978" },
    { city: "花蓮縣萬榮鄉", zip: "979" },
    { city: "花蓮縣玉里鎮", zip: "981" },
    { city: "花蓮縣卓溪鄉", zip: "982" },
    { city: "花蓮縣富里鄉", zip: "983" }
];

function ChangeZipCode(elem) {
    const nameList = Object.values(AutoAddrData).map(item => item.city);
    var city = $(elem).val().substr(0, 6);
    if (jQuery.inArray(city, nameList) !== -1) {
        $.each(AutoAddrData, function (index, val) {
            if (val.city == city) {
                $(elem).next().next().val(val.zip);
            }
        });
    }
    else if ($(elem).val().substr(0, 3) == "新竹市") {
        $(elem).next().next().val(300);
    }
    else if ($(elem).val().substr(0, 3) == "嘉義市") {
        $(elem).next().next().val(600);
    }
    else if ($(elem).val().substr(0, 5) == "臺中市中區") {
        $(elem).next().next().val(400);
    }
    else if ($(elem).val().substr(0, 5) == "臺中市東區") {
        $(elem).next().next().val(401);
    }
    else if ($(elem).val().substr(0, 5) == "臺中市南區") {
        $(elem).next().next().val(402);
    }
    else if ($(elem).val().substr(0, 5) == "臺中市西區") {
        $(elem).next().next().val(403);
    }
    else if ($(elem).val().substr(0, 5) == "臺中市北區") {
        $(elem).next().next().val(404);
    }
    else if ($(elem).val().substr(0, 5) == "臺南市東區") {
        $(elem).next().next().val(701);
    }
    else if ($(elem).val().substr(0, 5) == "臺南市南區") {
        $(elem).next().next().val(702);
    }
    else if ($(elem).val().substr(0, 5) == "臺南市西區") {
        $(elem).next().next().val(703);
    }
    else if ($(elem).val().substr(0, 5) == "臺南市北區") {
        $(elem).next().next().val(704);
    }
    else if ($(elem).val().substr(0, 7) == "嘉義縣阿里山鄉") {
        $(elem).next().next().val(605);
    }
    else if ($(elem).val().substr(0, 7) == "高雄市那瑪夏區") {
        $(elem).next().next().val(849);
    }
    else if ($(elem).val().substr(0, 7) == "屏東縣三地門鄉") {
        $(elem).next().next().val(901);
    }
    else if ($(elem).val().substr(0, 7) == "臺東縣太麻里鄉") {
        $(elem).next().next().val(963);
    }
    else {
        $(elem).next().next().val("");
    }
}
