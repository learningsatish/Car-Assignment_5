package com.example.demo.entity;

import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;


@Entity
public class Customer {
          @Id
          @GeneratedValue(strategy = GenerationType.AUTO)
          private Integer customerid;
          private String customername;
          private String carname;
          private String salesperson;
          
         @OneToOne(cascade = CascadeType.ALL)
      	@JoinColumn(name="car_id", referencedColumnName = "carid")
      	CarDetails cardetails;

		public Integer getCustomerid() {
			return customerid;
		}
		public void setCustomerid(Integer customerid) {
			this.customerid = customerid;
		}
		public String getCustomername() {
			return customername;
		}
		public void setCustomername(String customername) {
			this.customername = customername;
		}
		public String getCarname() {
			return carname;
		}
		public void setCarname(String carname) {
			this.carname = carname;
		}
		public String getSalesperson() {
			return salesperson;
		}
		public void setSalesperson(String salesperson) {
			this.salesperson = salesperson;
		}
		public CarDetails getCardetails() {
			return cardetails;
		}
		public void setCardetails(CarDetails cardetails) {
			this.cardetails = cardetails;
		}
          
}
