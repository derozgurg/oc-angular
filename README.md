# oc-angular 



**install**

bower install oc-angular --save


**usage**

**Components :**

ocPopup

	var eventClick =  function(calEvent, jsEvent, view) {
	    var eventPopup = $ocPopup.show({
	        event: jsEvent,
	        controller: "taskEventModCtrl",
	        resolve: {
	            title: function () {
	                return "Deneme Lan bu "
	            }
	        },
	        minWidth: 400,
	        windowClass: 'edit-modal-window modal-sm',
	        templateUrl: _modulePath + '/task/taskevent-mod.html?v=' + Math.random()
	    });
	
	    eventPopup.then(function () {
	        eventPopup = null;
	    })
	}


ocFullcalendar

	<div oc-fullcalendar="customer_calendar" calender-options="calenderOptions"></div>

	$scope.calenderOptions = {
        lang: 'tr',     
        timezone:"local",
        editable: false,
        allDaySlot: true,
        selectable: true,
        timeFormat:'h:mm',
        themeButtonIcons:{
            prev: 'btn btn-default',
            next: 'btn btn-default-e',
            prevYear: 'seek-prev',
            nextYear: 'seek-next'
        },
       header: {
            left: 'month agendaWeek agendaDay',
            center: 'title',
            right: 'today prev,next'
        },
        eventClick: function(calEvent, jsEvent, view) {
            var eventPopup = $ocPopup.show({
                event: jsEvent,
                controller: "taskEventModCtrl",
                resolve: {
                    taskEvent: function () {
                        return calEvent.data;
                    }
                },
                minWidth: 400,
                windowClass: 'edit-modal-window modal-sm',
                templateUrl: _modulePath + '/task/taskevent-mod.html
            });

            eventPopup.then(function (res) {
                console.log(res);
                eventPopup = null;
            });
        }       
    };
	
	//CALENDAR DELEGETE
	$ocFullCalendarDelegate.getDelegate("customer_calendar").then(function(delegete) {
		var calendarDelegete = delegete;
		calendarDelegete.removeEvents(lastEvents);
		oc.emptyArray(lastEvents);
		calendarDelegete.addEvents(newEvents);
	});



ocGmapPositionSelector

ocMultiSelectBox

ocDragDrop

ocSelect2

ocTableSortable

ocInfiniteScroll

ocBoostrapDatetimepicker
