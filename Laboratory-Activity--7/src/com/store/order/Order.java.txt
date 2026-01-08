package com.store.order;

public abstract class Order {

    private int orderId;
    private double amount;
    private OrderStatus status;

    public Order(int orderId, double amount) {
        this.orderId = orderId;
        this.amount = amount;
        this.status = OrderStatus.PENDING;
    }

    public abstract void processOrder();

    public String getOrderSummary() {
        return "Order ID: " + orderId +
               ", Amount: " + amount +
               ", Status: " + status;
    }

    // Getters (Encapsulation)
    public int getOrderId() {
        return orderId;
    }

    public double getAmount() {
        return amount;
    }

    public OrderStatus getStatus() {
        return status;
    }

    // Setter with validation
    public void setAmount(double amount) {
        if (amount >= 0) {
            this.amount = amount;
        }
    }

    // Protected so subclasses can update status safely
    protected void setStatus(OrderStatus status) {
        this.status = status;
    }
}
